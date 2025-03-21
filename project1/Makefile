# Define the compiler and flags
CXX      = g++
CXXFLAGS = -Wall -std=c++17

# List source files and automatically generate object file names
SOURCES_FCM  = fcm.cpp FCMModel.cpp
SOURCES_GEN  = generator.cpp FCMModel.cpp
SOURCES_EDIT = editor.cpp FCMModel.cpp RFCMModel.cpp
SOURCES_TEST = tests.cpp
OBJECTS_FCM  = $(SOURCES_FCM:.cpp=.o)
OBJECTS_GEN  = $(SOURCES_GEN:.cpp=.o)
OBJECTS_EDIT = $(SOURCES_EDIT:.cpp=.o)
OBJECTS_TEST = $(SOURCES_TEST:.cpp=.o)
TARGET_FCM   = fcm
TARGET_GEN   = generator
TARGET_EDIT  = editor
TARGET_TEST  = tests


# Default target to build both executables
all: clean $(TARGET_FCM) $(TARGET_GEN) $(TARGET_EDIT) $(TARGET_TEST)

# Link object files into the final executables
$(TARGET_FCM): $(OBJECTS_FCM)
	$(CXX) $(CXXFLAGS) -o $(TARGET_FCM) $(OBJECTS_FCM)

$(TARGET_GEN): $(OBJECTS_GEN)
	$(CXX) $(CXXFLAGS) -o $(TARGET_GEN) $(OBJECTS_GEN)

$(TARGET_EDIT): $(OBJECTS_EDIT)
	$(CXX) $(CXXFLAGS) -o $(TARGET_EDIT) $(OBJECTS_EDIT)

$(TARGET_TEST): $(OBJECTS_TEST)
	$(CXX) $(CXXFLAGS) -o $(TARGET_TEST) $(OBJECTS_TEST)

# Rule for compiling .cpp files into .o files
%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Clean up generated files
clean:
	rm -f $(TARGET_FCM) $(TARGET_GEN) $(TARGET_EDIT) $(TARGET_TEST) $(OBJECTS_FCM) $(OBJECTS_GEN) $(OBJECTS_EDIT) $(OBJECTS_TEST)
