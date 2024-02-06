# com_makefile


这是一个简单的MAKEFILE框架，方便后续开发

若要建立一个新的目录，则拷贝com目录，需修改新建目录下的TARGET，该变量为这么目录下的文件都编译成的.a文件名称。还需修改根目录下的Makefile中的L3_LIB_DIR，添加新生成的.a文件，以及L3_SUBDIRS中添加新创建的文件。
若引入新的库，根目录下Makefile中的L3_LIB_DIR添加-L新动态库的路径 -l库名，如 -L$(GNB_ROOT)/gNB_CU/cu_cp/common/utils/lib/ -lcucpcommonutils
