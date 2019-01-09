# sqlite

sqlite3 for secure

# build

* windows

	windows下使用以下命令来生成Visual Studio的解决方案(以vs2013为例)

	```shell
	$ cd sqlite3
	$ mkdir msvc && cd msvc
	$ cmake .. -G "Visual Studio 12 2013"
	```

* linux

	```shell
	$ cd sqlite3
	$ mkdir build && cd build
	$ cmake ..
	$ make
	```