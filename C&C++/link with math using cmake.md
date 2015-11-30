1.通过命令行可以在最后加上 -lm   ，我想应该是 link m 的意思吧，参考下面这个链接
http://stackoverflow.com/questions/8671366/undefined-reference-to-pow-and-floor

2.下面两条链接告诉了我怎么用 CMakeLists.txt 自定义要链接的库，包括最基本的 math
只需这样    target_link_libraries(untitled1 m)		// untitled1这里是 target_name
http://www.cs.swarthmore.edu/~adanner/tips/cmake.php
https://devnet.jetbrains.com/thread/472180


* here is another answer about how C++ libraries work:
http://stackoverflow.com/questions/12645117/undefined-reference-errors-after-running-cmake