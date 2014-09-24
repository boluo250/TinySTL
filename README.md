TinySTL
=======
采用C++11实现一款简易的STL标准库

目的：练习数据结构与算法和C++ Template编程

编译环境：VS2013及以上版本

##开发计划：
  * STL的几大基本组件，如string、vector、list、deque、set、map、unordered_\*等
  * STL算法库中的大部分算法
  * circular buffer
  * bitmap
  * skip list
  * binary search tree
  * AVL tree
  * splay tree
  * rope
  * Van Emde Boas tree
  * treap
  * B-tree
  * trie
  * suffix array/tree
  * Disjoint-set data structure
  * k-d tree
  * R-tree
  * Graph

##完成进度：
* STL的几大基本组件
    * type traits：100%  
    * 空间配置器：100%
    * iterator traits：100%
    * reverse_iterator：100%
    * vector：100%
* STL Algorithms:  
    * fill：100% 
    * fill_n：100% 
* circular_buffer：100%   

#TinySTL测试:
###测试环境：Windows 7 && VS2013 && release模式
###测试结果：
    //std::vector<int> vec;
    TinySTL::vector<int> vec;
	ProfilerInstance::start();
	int i = 0;
	for (; i != 10000; ++i){
		vec.push_back(i);
	}
	ProfilerInstance::finish();
	ProfilerInstance::dumpDuringTime();
    
######i = 100000 -> (TinySTL::vector<int>：2ms \\ std::vector<int>：6ms)
######i = 1000000 -> (TinySTL::vector<int>：11ms \\ std::vector<int>：16ms)
######i = 10000000 -> (TinySTL::vector<int>：129ms \\ std::vector<int>：210ms)  
    //std::vector<std::string> vec;
    TinySTL::vector<std::string> vec;
	ProfilerInstance::start();
	int i = 0;
	for (; i != 10000; ++i){
		vec.push_back(std::string("zouxiaohang"));
	}
	ProfilerInstance::finish();
	ProfilerInstance::dumpDuringTime();
    
######i = 100000 -> (TinySTL::vector<int>：18ms \\ std::vector<int>：29ms)
######i = 1000000 -> (TinySTL::vector<int>：181ms \\ std::vector<int>：232ms)
######i = 10000000 -> (TinySTL::vector<int>：2372ms \\ std::vector<int>：1972ms)
    TinySTL::circular_buffer<int, 10000> cb(10000, 0);
    //boost::circular_buffer<int> cb(10000, 0);
	ProfilerInstance::start();
	for (int i = 0; i != 10000000; ++i){
		cb.push_back(i);
	}
	ProfilerInstance::finish();
	ProfilerInstance::dumpDuringTime();
    
######i = 10000000 -> (TinySTL::circular_buffer：75ms \\ boost::circular_buffer：22ms)
######i = 100000000 -> (TinySTL::circular_buffer：604ms \\ boost::circular_buffer：252ms)
######i = 1000000000 -> (TinySTL::circular_buffer：5936ms \\ boost::circular_buffer：2241ms)



