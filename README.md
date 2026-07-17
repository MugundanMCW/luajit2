METIC_PYTHON_VERSION=3.13 --repo_env=TF_PYTHON_VERSION=3.13 --local_resources=memory=HOST_RAM*0.5 --jobs=4 --@com_google_absl//absl:use_dlls=False --@com_google_protobuf//build_defs:use_dlls=False //tensorflow/tools/pip_package:wheel --verbose_failures
WARNING: Ignoring JAVA_HOME, because it must point to a JDK, not a JRE.
WARNING: The following configs were expanded more than once: [clang_local]. For repeatable flags, repeats are counted twice and may lead to unexpected behavior.
INFO: Reading 'startup' options from c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --windows_enable_symlinks
INFO: Options provided by the client:
  Inherited 'common' options: --isatty=1 --terminal_columns=120
INFO: Reading rc options for 'build' from c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc:
  Inherited 'common' options: --repo_env=ML_WHEEL_TYPE=snapshot --repo_env=ML_WHEEL_BUILD_DATE= --repo_env=ML_WHEEL_VERSION_SUFFIX= --incompatible_default_to_explicit_init_py --define framework_shared_object=true --define tsl_protobuf_header_only=true --define=allow_oversize_protos=true --spawn_strategy=standalone -c opt --repo_env=USE_PYWRAP_RULES=True --copt=-DGRPC_BAZEL_BUILD --host_copt=-DGRPC_BAZEL_BUILD --action_env=GRPC_BAZEL_RUNTIME=1 --repo_env=PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=upb --action_env=PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=upb --@rules_python//python/config_settings:precompile=force_disabled --@rules_python//python/config_settings:bootstrap_impl=script --repo_env=RULES_PYTHON_ENABLE_PIPSTAR=0 --announce_rc --define=grpc_no_ares=true --noincompatible_remove_legacy_whole_archive --enable_platform_specific_config --define=with_xla_support=true --config=short_logs --config=v2 --@rules_python//python/config_settings:precompile=force_disabled --experimental_cc_shared_library --experimental_link_static_libraries_once=false --incompatible_enforce_config_setting_visibility --noenable_bzlmod --enable_workspace --incompatible_enable_cc_toolchain_resolution --repo_env USE_HERMETIC_CC_TOOLCHAIN=1 --experimental_repo_remote_exec --java_runtime_version=remotejdk_21
INFO: Options provided by the client:
  'build' options: --python_path=C:/Users/HCKTest/AppData/Local/Programs/Python/Python313-arm64/python.exe
INFO: Found applicable config definition common:short_logs in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --output_filter=DONT_MATCH_ANYTHING
INFO: Found applicable config definition common:v2 in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --define=tf_api_version=2 --action_env=TF2_BEHAVIOR=1
INFO: Found applicable config definition common:release_cpu_windows_arm64_minimal in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --config=release_cpu_windows_arm64 --config=nogcp --config=nonccl --define=disable_tf_lite_py=true --define=with_tpu_support=false
INFO: Found applicable config definition common:release_cpu_windows_arm64 in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --config=release_base --config=win_arm64_clang --define=no_tensorflow_py_deps=true --define=with_xla_support=false
INFO: Found applicable config definition common:release_base in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --config=cpu_cross
INFO: Found applicable config definition common:cpu_cross in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --define=with_cross_compiler_support=true
INFO: Found applicable config definition common:win_arm64_clang in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --config=win_clang_base --config=clang_local --cpu=arm64_windows --extra_toolchains=@local_config_cc//:cc-toolchain-arm64_windows-clang-cl --extra_execution_platforms=//tensorflow/tools/toolchains/win2022:windows_ltsc2022_arm64 --host_platform=//tensorflow/tools/toolchains/win2022:windows_ltsc2022_arm64 --platforms=//tensorflow/tools/toolchains/win2022:windows_ltsc2022_arm64 --linkopt=/MACHINE:ARM64 --host_linkopt=/MACHINE:ARM64 --define=tensorflow_mkldnn_contraction_kernel=0 --define=xnn_enable_avxvnniint8=false --define=xnn_enable_avx512fp16=false --define=xnn_enable_sme2=false --define=ynn_enable_arm64_sme=false --define=ynn_enable_arm64_sme2=false --define=with_onednn_v3=false --define=build_with_mkl=false --define=enable_mkl=false --define=no_nccl_support=true --repo_env=TF_NEED_CUDA=0 --repo_env=TF_NEED_ROCM=0 --repo_env=HERMETIC_PYTHON_VERSION=3.13 --repo_env=TF_PYTHON_VERSION=3.13 --action_env=CLANG_COMPILER_PATH=C:/Program Files/LLVM/bin/clang-cl.exe --repo_env=CC=C:/Program Files/LLVM/bin/clang-cl.exe --repo_env=BAZEL_COMPILER=C:/Program Files/LLVM/bin/clang-cl.exe --features=-absolute_includes --host_features=-absolute_includes --@rules_python//python/config_settings:bootstrap_impl=zip --build_python_zip --action_env=PYTHON=C:/Users/HCKTest/AppData/Local/Programs/Python/Python313-arm64/python.exe
INFO: Found applicable config definition common:win_clang_base in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --@com_google_protobuf//build_defs:use_dlls=True --@com_google_absl//absl:use_dlls=True --linkopt=/demangle:no --host_linkopt=/demangle:no --linkopt=/errorlimit:0 --host_linkopt=/errorlimit:0 --copt=/clang:-Weverything --host_copt=/clang:-Weverything --compiler=clang-cl --linkopt=/FORCE:MULTIPLE --host_linkopt=/FORCE:MULTIPLE --action_env=PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.PY;.PYW --features=-absolute_includes --host_features=-absolute_includes
INFO: Found applicable config definition common:clang_local in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --noincompatible_enable_cc_toolchain_resolution --noincompatible_enable_android_toolchain_resolution --@rules_ml_toolchain//common:enable_hermetic_cc=False --repo_env USE_HERMETIC_CC_TOOLCHAIN=0
INFO: Found applicable config definition common:nogcp in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --define=no_gcp_support=true
INFO: Found applicable config definition common:nonccl in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --define=no_nccl_support=true
INFO: Found applicable config definition common:windows in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --copt=/W0 --host_copt=/W0 --copt=/Zc:__cplusplus --host_copt=/Zc:__cplusplus --copt=/D_USE_MATH_DEFINES --host_copt=/D_USE_MATH_DEFINES --features=compiler_param_file --features=archive_param_file --copt=/d2ReducedOptimizeHugeFunctions --host_copt=/d2ReducedOptimizeHugeFunctions --copt=-D_ENABLE_EXTENDED_ALIGNED_STORAGE --host_copt=-D_ENABLE_EXTENDED_ALIGNED_STORAGE --enable_runfiles --nobuild_python_zip --dynamic_mode=off --cxxopt=/std:c++17 --host_cxxopt=/std:c++17 --config=monolithic --copt=-DWIN32_LEAN_AND_MEAN --host_copt=-DWIN32_LEAN_AND_MEAN --copt=-DNOGDI --host_copt=-DNOGDI --copt=/Zc:preprocessor --host_copt=/Zc:preprocessor --linkopt=/DEBUG --host_linkopt=/DEBUG --linkopt=/OPT:REF --host_linkopt=/OPT:REF --linkopt=/OPT:ICF --host_linkopt=/OPT:ICF --verbose_failures --features=compiler_param_file --config=clang_local --define=xnn_enable_avx512fp16=false --config=no_tfrt
INFO: Found applicable config definition common:monolithic in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --define framework_shared_object=false --define tsl_protobuf_header_only=false --experimental_link_static_libraries_once=false
INFO: Found applicable config definition common:clang_local in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --noincompatible_enable_cc_toolchain_resolution --noincompatible_enable_android_toolchain_resolution --@rules_ml_toolchain//common:enable_hermetic_cc=False --repo_env USE_HERMETIC_CC_TOOLCHAIN=0
INFO: Found applicable config definition common:no_tfrt in file c:\users\hcktest\desktop\mugunth\source\tensorflow\.bazelrc: --deleted_packages=tensorflow/compiler/mlir/tfrt,tensorflow/compiler/mlir/tfrt/benchmarks,tensorflow/compiler/mlir/tfrt/ir,tensorflow/compiler/mlir/tfrt/ir/mlrt,tensorflow/compiler/mlir/tfrt/jit/python_binding,tensorflow/compiler/mlir/tfrt/jit/transforms,tensorflow/compiler/mlir/tfrt/python_tests,tensorflow/compiler/mlir/tfrt/tests,tensorflow/compiler/mlir/tfrt/tests/ifrt,tensorflow/compiler/mlir/tfrt/tests/mlrt,tensorflow/compiler/mlir/tfrt/tests/ir,tensorflow/compiler/mlir/tfrt/tests/analysis,tensorflow/compiler/mlir/tfrt/tests/jit,tensorflow/compiler/mlir/tfrt/tests/lhlo_to_tfrt,tensorflow/compiler/mlir/tfrt/tests/lhlo_to_jitrt,tensorflow/compiler/mlir/tfrt/tests/tf_to_corert,tensorflow/compiler/mlir/tfrt/tests/tf_to_tfrt_data,tensorflow/compiler/mlir/tfrt/tests/saved_model,tensorflow/compiler/mlir/tfrt/transforms/lhlo_gpu_to_tfrt_gpu,tensorflow/compiler/mlir/tfrt/transforms/mlrt,tensorflow/core/runtime_fallback,tensorflow/core/runtime_fallback/conversion,tensorflow/core/runtime_fallback/kernel,tensorflow/core/runtime_fallback/opdefs,tensorflow/core/runtime_fallback/runtime,tensorflow/core/runtime_fallback/util,tensorflow/core/runtime_fallback/test,tensorflow/core/runtime_fallback/test/gpu,tensorflow/core/runtime_fallback/test/saved_model,tensorflow/core/runtime_fallback/test/testdata,tensorflow/core/tfrt/stubs,tensorflow/core/tfrt/tfrt_session,tensorflow/core/tfrt/mlrt,tensorflow/core/tfrt/mlrt/attribute,tensorflow/core/tfrt/mlrt/kernel,tensorflow/core/tfrt/mlrt/bytecode,tensorflow/core/tfrt/mlrt/interpreter,tensorflow/compiler/mlir/tfrt/translate/mlrt,tensorflow/compiler/mlir/tfrt/translate/mlrt/testdata,tensorflow/core/tfrt/gpu,tensorflow/core/tfrt/run_handler_thread_pool,tensorflow/core/tfrt/runtime,tensorflow/core/tfrt/saved_model,tensorflow/core/tfrt/graph_executor,tensorflow/core/tfrt/saved_model/tests,tensorflow/core/tfrt/tpu,tensorflow/core/tfrt/utils,tensorflow/core/tfrt/utils/debug,tensorflow/core/tfrt/saved_model/python,tensorflow/core/tfrt/graph_executor/python,tensorflow/core/tfrt/saved_model/utils
WARNING: The following configs were expanded more than once: [clang_local]. For repeatable flags, repeats are counted twice and may lead to unexpected behavior.
WARNING: Build options --@@com_google_absl//absl:use_dlls and --@@com_google_protobuf//build_defs:use_dlls have changed, discarding analysis cache (this can be expensive, see https://bazel.build/advanced/performance/iteration-speed).
INFO: Analyzed target //tensorflow/tools/pip_package:wheel (0 packages loaded, 52392 targets configured).
ERROR: C:/users/hcktest/desktop/mugunth/source/tensorflow/tensorflow/python/BUILD:1570:15: Linking tensorflow/python/_pywrap_tensorflow_common.dll failed: (Exit 1): lld-link.exe failed: error executing CppLink command (from target //tensorflow/python:_pywrap_tensorflow_common.dll)
  cd /d C:/users/hcktest/_bazel_hcktest/b73u5zlo/execroot/org_tensorflow
  SET CLANG_COMPILER_PATH=C:/Program Files/LLVM/bin/clang-cl.exe
    SET GRPC_BAZEL_RUNTIME=1
    SET LIB=C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\ATLMFC\lib\arm64;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\lib\arm64;C:\Program Files (x86)\Windows Kits\10\lib\10.0.26100.0\ucrt\arm64;C:\Program Files (x86)\Windows Kits\10\\lib\10.0.26100.0\\um\arm64;C:\Program Files\LLVM\lib\clang\21\lib\windows
    SET PATH=C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\bin\HostX64\arm64;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\bin\HostX64\x64;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\VC\VCPackages;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\TestWindow;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer;C:\Program Files\Microsoft Visual Studio\2022\Community\MSBuild\Current\bin\Roslyn;C:\Program Files\Microsoft Visual Studio\2022\Community\Team Tools\DiagnosticsHub\Collector;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin;C:\Program Files (x86)\Windows Kits\10\bin\10.0.26100.0\\x64;C:\Program Files (x86)\Windows Kits\10\bin\\x64;C:\Program Files\Microsoft Visual Studio\2022\Community\\MSBuild\Current\Bin\arm64;C:\Windows\Microsoft.NET\Framework64\v4.0.30319;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\;;C:\windows\system32;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\Ninja;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\VC\Linux\bin\ConnectionManagerExe;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\vcpkg
    SET PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.PY;.PYW
    SET PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=upb
    SET PWD=/proc/self/cwd
    SET PYTHON=C:/Users/HCKTest/AppData/Local/Programs/Python/Python313-arm64/python.exe
    SET TEMP=C:\Users\HCKTest\AppData\Local\Temp
    SET TF2_BEHAVIOR=1
    SET TMP=C:\Users\HCKTest\AppData\Local\Temp
  C:\Program Files\LLVM\bin\lld-link.exe @bazel-out/arm64_windows-opt/bin/tensorflow/python/_pywrap_tensorflow_common.dll-2.params
# Configuration: de500abd4431a17b7131b0a0266533e95c8ac0587082a20f913ed20ef688ec3a
# Execution platform: //tensorflow/tools/toolchains/win2022:windows_ltsc2022_arm64
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-ldl'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lpthread'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: ignoring unknown argument '-lm'
lld-link: warning: duplicate symbol: ?GetXlaSparseCoreStackingMemLimit@tensorflow@@YA_JXZ
>>> defined at sparse_core_ops_utils.lib(sparse_core_ops_utils.obj)

lld-link: warning: duplicate symbol: ?GetXlaSparseCoreStackingTableShardLimit@tensorflow@@YA_JXZ
>>> defined at sparse_core_ops_utils.lib(sparse_core_ops_utils.obj)

lld-link: error: <root>: undefined symbol: ?PrepareInsertLarge@container_internal@lts_20260526@absl@@YA_KAEAVCommonFields@123@AEBUPolicyFunctions@123@_KV?$NonIterableBitMask@I$0BA@$0A@@123@UFindInfo@123@@Z
lld-link: warning: converter_python_api.lo.lib(converter_python_api.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: converter_python_api.lo.lib(converter_python_api.obj): locally defined symbol imported: TF_NewKernelBuilder (defined in kernels.lib(kernels.obj)) [LNK4217]
lld-link: warning: converter_python_api.lo.lib(converter_python_api.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: converter_python_api.lo.lib(converter_python_api.obj): locally defined symbol imported: TF_RegisterKernelBuilder (defined in kernels.lib(kernels.obj)) [LNK4217]
lld-link: warning: converter_python_api.lo.lib(converter_python_api.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: threadpool_listener.lib(threadpool_listener.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_NewOpDefinitionBuilder (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddInput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddAttr (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderSetShapeInferenceFunction (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_RegisterOpDefinition (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_ShapeInferenceContextScalar (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_ShapeInferenceContextSetOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: histogram_summary_op_lib.lo.lib(histogram_summary.obj): locally defined symbol imported: TF_DeleteShapeHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_NewOpDefinitionBuilder (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddInput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddAttr (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderSetShapeInferenceFunction (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_RegisterOpDefinition (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_ShapeInferenceContextScalar (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_ShapeInferenceContextSetOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: merge_summary_op_lib.lo.lib(merge_summary.obj): locally defined symbol imported: TF_DeleteShapeHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_NewOpDefinitionBuilder (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddInput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddAttr (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_OpDefinitionBuilderSetShapeInferenceFunction (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_RegisterOpDefinition (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_ShapeInferenceContextScalar (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_ShapeInferenceContextSetOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: summary_op_lib.lo.lib(summary.obj): locally defined symbol imported: TF_DeleteShapeHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: batch_kernels.lo.lib(batch_kernels.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: batch_kernels.lo.lib(batch_kernels.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: batch_kernels.lo.lib(batch_kernels.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: batch_kernels.lo.lib(batch_kernels.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: batch_kernels.lo.lib(batch_kernels.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: batch_kernels.lo.lib(batch_kernels.obj): locally defined symbol imported: ?DEVICE_DEFAULT@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: batch_resource_base.lib(batch_resource_base.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: batch_resource_base.lib(batch_resource_base.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: batch_resource_base.lib(batch_resource_base.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: tensor_shape_utils.lib(tensor_shape_utils.obj): locally defined symbol imported: TF_NumDims (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: tensor_shape_utils.lib(tensor_shape_utils.obj): locally defined symbol imported: TF_Dim (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: window_dataset.lib(window_dataset.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_NewOpDefinitionBuilder (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddInput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_OpDefinitionBuilderAddAttr (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_OpDefinitionBuilderSetShapeInferenceFunction (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_RegisterOpDefinition (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_NewShapeHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextGetInput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextRankKnown (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContext_GetAttrType (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_DataTypeSize (defined in tf_datatype.lo.lib(tf_datatype.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextWithRankAtLeast (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_NewDimensionHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextDim (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_DimensionHandleValueKnown (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_DimensionHandleValue (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextSubshape (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextSetUnknownShape (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_DeleteShapeHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextVectorFromSize (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextConcatenateShapes (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_ShapeInferenceContextSetOutput (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: bitcast_op_lib.lo.lib(bitcast.obj): locally defined symbol imported: TF_DeleteDimensionHandle (defined in ops.lo.lib(ops.obj)) [LNK4217]
lld-link: warning: ragged_tensor_variant.lib(ragged_tensor_variant.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: metric_utils.lib(metric_utils.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: captured_function.lib(captured_function.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: captured_function.lib(captured_function.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: captured_function.lib(captured_function.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: captured_function.lib(captured_function.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: snapshot_utils.lib(snapshot_utils.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: snapshot_utils.lib(snapshot_utils.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: snapshot_utils.lib(snapshot_utils.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: tf_rendezvous_c_api_internal.lib(tf_rendezvous_c_api_internal.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: tf_rendezvous_c_api_internal.lib(tf_rendezvous_c_api_internal.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: tf_rendezvous_c_api_internal.lib(tf_rendezvous_c_api_internal.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: tf_device_context_c_api_internal.lib(tf_device_context_c_api_internal.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: stream_executor.lib(stream_executor.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: stream_executor.lib(stream_executor.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: stream_executor.lib(stream_executor.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: stream_executor.lib(stream_executor.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: tpu_rewrite_device_util.lib(tpu_rewrite_device_util.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: device_util.lib(device_util.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_op_registry.lo.lib(xla_op_registry.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_op_registry.lo.lib(xla_op_registry.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_helpers.lo.lib(xla_helpers.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_helpers.lo.lib(xla_helpers.obj): locally defined symbol imported: ?DEVICE_TPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_helpers.lo.lib(xla_helpers.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_cluster_util.lib(xla_cluster_util.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: local_device_state.lib(local_device_state.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: local_device_state.lib(local_device_state.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: backend.lib(backend.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: backend.lib(backend.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: arithmetic_optimizer.lib(arithmetic_optimizer.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: arithmetic_optimizer.lib(arithmetic_optimizer.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: memory_optimizer.lib(memory_optimizer.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: memory_optimizer.lib(memory_optimizer.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: pin_to_host_optimizer.lib(pin_to_host_optimizer.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: pin_to_host_optimizer.lib(pin_to_host_optimizer.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: evaluation_utils.lib(evaluation_utils.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: gpu_id_impl.lib(gpu_id_manager.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: utils.lib(utils.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: utils.lib(utils.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: eval_utils.lib(eval_utils.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: Pass.lib(pass.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: Pass.lib(pass.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: pdll_utils.lib(utils.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: tf_ops_device_helper.lib(tf_ops_device_helper.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: bfc_allocator.lib(bfc_allocator.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: bfc_allocator.lib(bfc_allocator.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: bfc_allocator.lib(bfc_allocator.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: allocator_registry_impl.lo.lib(cpu_allocator_impl.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: allocator_registry_impl.lo.lib(cpu_allocator_impl.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: allocator_registry_impl.lo.lib(cpu_allocator_impl.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: traceme_recorder_impl.lo.lib(traceme_recorder.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_NewBufferFromString (defined in tf_buffer.lib(tf_buffer.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_NewCustomDeviceTensorHandle (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleDeviceName (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleResolve (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleCopySharingTensor (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_DeleteTensorHandle (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_NewBuffer (defined in tf_buffer.lib(tf_buffer.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpAttrsSerialize (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_DeleteBuffer (defined in tf_buffer.lib(tf_buffer.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleDevicePointer (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_NewTensorHandleFromTensor (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleDataType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleNumDims (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleDim (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleCopyToDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_TensorData (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpGetContext (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpGetName (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpGetAttrs (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpGetFlatInputCount (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpGetFlatInput (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_TensorHandleNumElements (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_NewOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TF_NewTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpSetDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpSetAttrTensor (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_OpSetAttrType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_Execute (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_cc.lib(dtensor_device.obj): locally defined symbol imported: TFE_DeleteOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TFE_TensorHandleDataType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TFE_TensorHandleResolve (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TFE_DeleteTensorHandle (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TFE_TensorHandleCopyToDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: dtensor_device_util.lib(dtensor_device_util.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TFE_TensorHandleNumElements (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TFE_TensorHandleDataType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TFE_TensorHandleResolve (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TF_TensorData (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: small_constant_optimization.lib(small_constant_optimization.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: get_compiler_ir.lo.lib(get_compiler_ir.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: get_compiler_ir.lo.lib(get_compiler_ir.obj): locally defined symbol imported: ?DEVICE_TPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: grappler.lib(grappler.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: grappler.lib(grappler.obj): locally defined symbol imported: TF_NewBuffer (defined in tf_buffer.lib(tf_buffer.obj)) [LNK4217]
lld-link: warning: grappler.lib(grappler.obj): locally defined symbol imported: TF_DeleteBuffer (defined in tf_buffer.lib(tf_buffer.obj)) [LNK4217]
lld-link: warning: grappler.lib(grappler.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: grappler.lib(grappler.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pluggable_profiler.lib(pluggable_profiler.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pluggable_profiler.lib(pluggable_profiler.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: next_pluggable_device_factory.lib(next_pluggable_device_factory.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: next_pluggable_device_factory.lib(next_pluggable_device_factory.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: next_pluggable_device.lib(next_pluggable_device_context.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: next_pluggable_device.lib(next_pluggable_device_context.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: next_pluggable_device.lib(next_pluggable_device_context.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: next_pluggable_device.lib(next_pluggable_device_context.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: next_pluggable_device.lib(next_pluggable_device_context.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: next_pluggable_device.lib(next_pluggable_device_context.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_DeleteOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_DeleteExecutor (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_DeleteTensorHandle (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_ExecutorWaitForAllPendingNodes (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_ExecutorClearError (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpReset (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpAddAttrs (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpAddInput (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_ContextSetExecutorForThread (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_NewOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpSetDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpSetCancellationManager (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_Execute (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_NewExecutor (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_TensorHandleCopyToDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_TensorHandleGetStatus (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_TensorHandleDataType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_NewTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpSetAttrTensor (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_OpSetAttrType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: parallel_device_lib.lib(parallel_device_lib.obj): locally defined symbol imported: TFE_ContextAsyncWait (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_DeleteOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpAddInput (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetCancellationManager (defined in c_api_experimental.lo.lib(c_api_experimental.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpGetAttrType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_Execute (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_DeleteContext (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_NewOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrFunctionList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrBoolList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrTypeList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrFloatList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrIntList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrStringList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrShapeList (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrInt (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_TensorHandleDataType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TF_RegisterLogListener (defined in c_api_no_xla.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrString (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrBool (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrFloat (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrShape (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tfe_src.obj): locally defined symbol imported: TFE_OpSetAttrFunctionName (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor_conversion.obj): locally defined symbol imported: TFE_DeleteTensorHandle (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleDataType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleResolve (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_NewOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_OpSetDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_OpAddInput (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_OpSetAttrType (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_OpSetAttrBool (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_Execute (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_DeleteOp (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_DeleteTensorHandle (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleCopyToDevice (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleNumElements (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleNumDims (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleDim (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleTensorDebugInfo (defined in c_api.lo.lib(c_api_debug.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorDebugInfoOnDeviceNumDims (defined in c_api.lo.lib(c_api_debug.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorDebugInfoOnDeviceDim (defined in c_api.lo.lib(c_api_debug.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_DeleteTensorDebugInfo (defined in c_api.lo.lib(c_api_debug.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleDeviceName (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: pywrap_tfe_lib.lib(pywrap_tensor.obj): locally defined symbol imported: TFE_TensorHandleBackingDeviceName (defined in c_api.lo.lib(c_api.obj)) [LNK4217]
lld-link: warning: py_seq_tensor.lib(py_seq_tensor.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_TensorType (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_DeleteTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_TensorData (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_TensorMaybeMove (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_TensorByteSize (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_NumDims (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_Dim (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: ndarray_tensor.lib(ndarray_tensor.obj): locally defined symbol imported: TF_NewTensor (defined in tf_tensor.lib(tf_tensor.obj)) [LNK4217]
lld-link: warning: modular_filesystem.lib(modular_filesystem_registration.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: modular_filesystem.lib(modular_filesystem_registration.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: modular_filesystem.lib(modular_filesystem.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: modular_filesystem.lib(modular_filesystem.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: modular_filesystem.lib(modular_filesystem.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: grpc_master_service.lo.lib(grpc_master_service.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: grpc_master_service.lo.lib(grpc_master_service.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: eager_service_impl.lib(eager_service_impl.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: eager_service_impl.lib(eager_service_impl.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: se_gpu_pjrt_client.lib(se_gpu_pjrt_client.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: se_gpu_pjrt_client.lib(se_gpu_pjrt_client.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: se_gpu_pjrt_client.lib(se_gpu_pjrt_client.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: gpu_helpers.lib(gpu_helpers.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: gpu_helpers.lib(gpu_helpers.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: allocator_memory_registration.lib(allocator_memory_registration.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: allocator_memory_registration.lib(allocator_memory_registration.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: gpu_cliques.lib(gpu_cliques.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: gpu_cliques.lib(gpu_cliques.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: gpu_cliques.lib(gpu_cliques.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: rendezvous.lib(rendezvous.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: rendezvous.lib(rendezvous.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: xla_ops_no_jit_rewrite_registration.lo.lib(xla_ops.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: xla_ops_no_jit_rewrite_registration.lo.lib(xla_ops.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: xla_ops_no_jit_rewrite_registration.lo.lib(xla_ops.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_ops_no_jit_rewrite_registration.lo.lib(xla_ops.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_ops_no_jit_rewrite_registration.lo.lib(xla_ops.obj): locally defined symbol imported: ?DEVICE_DEFAULT@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: compilation_passes.lib(mark_for_compilation_pass.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: compilation_passes.lib(encapsulate_xla_computations_pass.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: compilation_passes.lib(encapsulate_xla_computations_pass.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: device_util.lib(device_util.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: device_util.lib(device_util.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_platform_info.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_platform_info.obj): locally defined symbol imported: ?DEVICE_TPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_platform_info.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_ops_on_regular_devices.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_ops_on_regular_devices.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_device.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: xla_device_no_jit_rewrite_registration.lo.lib(xla_device.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_device_context.lib(pjrt_device_context.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_device_context.lib(pjrt_device_context.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_client.lib(pjrt_c_api_client.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_client.lib(pjrt_c_api_client.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_client.lib(pjrt_c_api_client.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_wrapper_impl.lib(pjrt_c_api_wrapper_impl.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_wrapper_impl.lib(pjrt_c_api_wrapper_impl.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_wrapper_impl.lib(pjrt_c_api_wrapper_impl.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_helpers.lib(pjrt_c_api_helpers.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_helpers.lib(pjrt_c_api_helpers.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_c_api_helpers.lib(pjrt_c_api_helpers.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: pjrt_stream_executor_client.lo.lib(pjrt_stream_executor_client.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_stream_executor_client.lo.lib(pjrt_stream_executor_client.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: pjrt_stream_executor_client.lo.lib(pjrt_stream_executor_client.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(host_to_device_transfer_manager.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(host_to_device_transfer_manager.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(host_to_device_transfer_manager.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(common_pjrt_client.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(common_pjrt_client.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(common_pjrt_client.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(abstract_tracked_device_buffer.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: common_pjrt_client.lib(abstract_tracked_device_buffer.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: transpose.lib(transpose.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: transpose.lib(transpose.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: transpose.lib(transpose.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: xla_launch_util.lib(xla_launch_util.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_launch_util.lib(xla_launch_util.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: xla_compile_util.lib(xla_compile_util.obj): locally defined symbol imported: ?DEVICE_TPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: execute.lib(execute.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: execute.lib(execute.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: execute.lib(execute.obj): locally defined symbol imported: ?DEVICE_TPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: execute.lib(execute.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: execute.lib(execute.obj): locally defined symbol imported: ?DEVICE_GPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: execute.lib(execute.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: remote_tensor_handle_data.lib(remote_tensor_handle_data.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: remote_tensor_handle_data.lib(remote_tensor_handle_data.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: collective_param_resolver_distributed.lib(collective_param_resolver_distributed.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: graph_mgr.lib(graph_mgr.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: graph_mgr.lib(graph_mgr.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: graph_mgr.lib(graph_mgr.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: stream_executor_allocator.lib(stream_executor_allocator.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: stream_executor_allocator.lib(stream_executor_allocator.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: mlir.lo.lib(mlir.obj): locally defined symbol imported: TF_SetStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: grpc_remote_master.lo.lib(grpc_remote_master.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: grpc_remote_master.lo.lib(grpc_remote_master.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: data_service_client.lib(data_service_client.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: data_service_client.lib(data_service_client.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: data_service_client.lib(data_service_client.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: snapshot_stream_writer.lib(snapshot_stream_writer.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: snapshot_stream_writer.lib(snapshot_stream_writer.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: parallel_tfrecord_writer.lib(parallel_tfrecord_writer.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: parallel_tfrecord_writer.lib(parallel_tfrecord_writer.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: python_hooks.lo.lib(python_hooks.obj): locally defined symbol imported: ?traceme_enabled@profiler@xla@@3U?$atomic@_N@std@@A (defined in traceme_state.lib(traceme_state.obj)) [LNK4217]
lld-link: warning: pjrt_cpu_client_registration.lo.lib(pjrt_cpu_client_registration.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: cpu_client.lib(cpu_client.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: cpu_client.lib(cpu_client.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: cpu_client.lib(cpu_client.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: abstract_cpu_buffer.lib(raw_buffer.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: abstract_cpu_buffer.lib(raw_buffer.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: jit_compiler.lib(jit_compiler.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: jit_compiler.lib(jit_compiler.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: jit_compiler.lib(jit_compiler.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: hlo_pass_pipeline.lib(hlo_pass_pipeline.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: hlo_pass_pipeline.lib(hlo_pass_pipeline.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: hlo_pass_pipeline.lib(hlo_pass_pipeline.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: fusion_compiler.lib(fusion_compiler.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: fusion_compiler.lib(fusion_compiler.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: fusion_compiler.lib(fusion_compiler.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: trace_pass_instrumentation.lib(trace_pass_instrumentation.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: trace_pass_instrumentation.lib(trace_pass_instrumentation.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: cpu_executable.lib(cpu_executable.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: cpu_executable.lib(cpu_executable.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: cpu_executable.lib(cpu_executable.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: thunk_executor.lib(thunk_executor.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: thunk_executor.lib(thunk_executor.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: thunk_executor.lib(thunk_executor.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: thunk.lib(thunk.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: in_process_communicator.lib(in_process_communicator.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: in_process_communicator.lib(in_process_communicator.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: in_process_communicator.lib(in_process_communicator.obj): locally defined symbol imported: ?g_enable_source_location@profiler@tsl@@3U?$atomic@_N@std@@A (defined in traceme_global_flags.lo.lib(traceme_global_flags.obj)) [LNK4217]
lld-link: warning: slinky_threadpool.lib(slinky_threadpool.obj): locally defined symbol imported: ?g_trace_level@internal@profiler@tsl@@3U?$atomic@H@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: slinky_threadpool.lib(slinky_threadpool.obj): locally defined symbol imported: ?g_trace_filter_bitmap@internal@profiler@tsl@@3U?$atomic@_K@std@@A (defined in traceme_recorder_impl.lo.lib(traceme_recorder.obj)) [LNK4217]
lld-link: warning: toco_python_api.lo.lib(toco_python_api.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: toco_python_api.lo.lib(toco_python_api.obj): locally defined symbol imported: TF_NewKernelBuilder (defined in kernels.lib(kernels.obj)) [LNK4217]
lld-link: warning: toco_python_api.lo.lib(toco_python_api.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: toco_python_api.lo.lib(toco_python_api.obj): locally defined symbol imported: TF_RegisterKernelBuilder (defined in kernels.lib(kernels.obj)) [LNK4217]
lld-link: warning: toco_python_api.lo.lib(toco_python_api.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: py_func_lib.lo.lib(py_func.obj): locally defined symbol imported: ?DEVICE_CPU@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: py_func_lib.lo.lib(py_func.obj): locally defined symbol imported: ?DEVICE_DEFAULT@tensorflow@@3QEBDEB (defined in tensor.lo.lib(types.obj)) [LNK4217]
lld-link: warning: tfprof_show.lib(tfprof_show.obj): locally defined symbol imported: TF_NewStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: tfprof_show.lib(tfprof_show.obj): locally defined symbol imported: TF_GetCode (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: tfprof_show.lib(tfprof_show.obj): locally defined symbol imported: TF_Message (defined in tf_status.lib(tf_status.obj)) [LNK4217]
lld-link: warning: tfprof_show.lib(tfprof_show.obj): locally defined symbol imported: TF_DeleteStatus (defined in tf_status.lib(tf_status.obj)) [LNK4217]
Target //tensorflow/tools/pip_package:wheel failed to build
ERROR: C:/users/hcktest/desktop/mugunth/source/tensorflow/tensorflow/tools/pip_package/BUILD:318:9 TFWheel tensorflow/tools/pip_package/wheel_house/tensorflow-2.22.0.dev0+selfbuilt-cp313-cp313-win_arm64.whl failed: (Exit 1): lld-link.exe failed: error executing CppLink command (from target //tensorflow/python:_pywrap_tensorflow_common.dll)
  cd /d C:/users/hcktest/_bazel_hcktest/b73u5zlo/execroot/org_tensorflow
  SET CLANG_COMPILER_PATH=C:/Program Files/LLVM/bin/clang-cl.exe
    SET GRPC_BAZEL_RUNTIME=1
    SET LIB=C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\ATLMFC\lib\arm64;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\lib\arm64;C:\Program Files (x86)\Windows Kits\10\lib\10.0.26100.0\ucrt\arm64;C:\Program Files (x86)\Windows Kits\10\\lib\10.0.26100.0\\um\arm64;C:\Program Files\LLVM\lib\clang\21\lib\windows
    SET PATH=C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\bin\HostX64\arm64;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.44.35207\bin\HostX64\x64;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\VC\VCPackages;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\TestWindow;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer;C:\Program Files\Microsoft Visual Studio\2022\Community\MSBuild\Current\bin\Roslyn;C:\Program Files\Microsoft Visual Studio\2022\Community\Team Tools\DiagnosticsHub\Collector;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\Llvm\x64\bin;C:\Program Files (x86)\Windows Kits\10\bin\10.0.26100.0\\x64;C:\Program Files (x86)\Windows Kits\10\bin\\x64;C:\Program Files\Microsoft Visual Studio\2022\Community\\MSBuild\Current\Bin\arm64;C:\Windows\Microsoft.NET\Framework64\v4.0.30319;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\;;C:\windows\system32;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\Ninja;C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\IDE\VC\Linux\bin\ConnectionManagerExe;C:\Program Files\Microsoft Visual Studio\2022\Community\VC\vcpkg
    SET PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.PY;.PYW
    SET PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=upb
    SET PWD=/proc/self/cwd
    SET PYTHON=C:/Users/HCKTest/AppData/Local/Programs/Python/Python313-arm64/python.exe
    SET TEMP=C:\Users\HCKTest\AppData\Local\Temp
    SET TF2_BEHAVIOR=1
    SET TMP=C:\Users\HCKTest\AppData\Local\Temp
  C:\Program Files\LLVM\bin\lld-link.exe @bazel-out/arm64_windows-opt/bin/tensorflow/python/_pywrap_tensorflow_common.dll-2.params
# Configuration: de500abd4431a17b7131b0a0266533e95c8ac0587082a20f913ed20ef688ec3a
# Execution platform: //tensorflow/tools/toolchains/win2022:windows_ltsc2022_arm64
INFO: Elapsed time: 155.899s, Critical Path: 24.03s
INFO: 1699 processes: 117 internal, 1582 local.
ERROR: Build did NOT complete successfully

C:\Users\HCKTest\Desktop\Mugunth\source\tensorflow>
