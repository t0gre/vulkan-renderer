# Vulkan renderer

based of https://vkguide.dev/ initially

all dependecies are included apart from the vulkan sdk. Just downloaded it,
unpackit and source setup-env.sh (and ideally add that to your .bashrc)

### for dev


touch Debug && cd Debug
setup ----- cmake -DCMAKE_BUILD_TYPE=Debug .. 
build ----- cmake --build .
run   ----- ./renderer 
or use launch.json for vscode 

### for release 

touch Release && cd Release
setup ----- cmake -DCMAKE_BUILD_TYPE=Release .. 
build ----- cmake --build .
run   ----- ./renderer 
 