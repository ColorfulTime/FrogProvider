include /opt/omi/share/omi.mak

DEFINES = MI_API_VERSION=2
PROVIDER = frog
SOURCES = $(wildcard *.c *.cpp)
CLASSES = XYZ_Frog 

$(LIBRARY): $(OBJECTS)
	$(CXX) $(CXXSHLIBFLAGS) $(OBJECTS) -o $(LIBRARY) $(CXXLIBS)

%.o: %.c
	$(CC) -c $(CFLAGS) $(INCLUDES) $< $(CLIBS) -o $@

%.o: %.cpp
	$(CXX) -c $(CXXFLAGS) $(INCLUDES) $< -o $@

reg:
	$(BINDIR)/omireg $(CURDIR)/$(LIBRARY)

gen:
	$(BINDIR)/omigen --cpp -m frog schema.mof XYZ_Frog

clean:
	rm -f $(LIBRARY) $(OBJECTS) $(PROVIDER).reg


