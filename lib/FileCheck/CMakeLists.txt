add_library(MUST_LLVMFileCheck FileCheck.cpp)

set_target_properties(MUST_LLVMFileCheck
        PROPERTIES
        CXX_STANDARD 14
        CXX_STANDARD_REQUIRED ON)

target_link_libraries(MUST_LLVMFileCheck PUBLIC MUST_LLVMSupport MUST_LLVMADT)
target_include_directories(MUST_LLVMFileCheck PUBLIC include)
