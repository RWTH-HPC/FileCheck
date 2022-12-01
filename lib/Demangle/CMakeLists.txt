add_library(MUST_LLVMDemangle
        Demangle.cpp
        ItaniumDemangle.cpp
        MicrosoftDemangle.cpp
        MicrosoftDemangleNodes.cpp
        RustDemangle.cpp
        DLangDemangle.cpp
        )

target_include_directories(MUST_LLVMDemangle PUBLIC include)
