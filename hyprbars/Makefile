CXXFLAGS = -shared -fPIC --no-gnu-unique -g -std=c++2b -Wno-narrowing -Wno-deprecated-declarations
INCLUDES = `pkg-config --cflags pixman-1 libdrm hyprland pangocairo libinput libudev wayland-server xkbcommon`
LIBS = `pkg-config --libs pangocairo`

SRC = main.cpp barDeco.cpp BarPassElement.cpp
TARGET = hyprbars.so

all: $(TARGET)

$(TARGET): $(SRC)
	$(CXX) $(CXXFLAGS) $(INCLUDES) $^ $> -o $@ $(LIBS) -O2

clean:
	rm ./$(TARGET)

meson-build:
	mkdir -p build
	cd build && meson .. && ninja

.PHONY: all meson-build clean
