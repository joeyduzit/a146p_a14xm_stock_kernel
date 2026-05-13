# Stock Kernel Source Code for Samsung A14 5G A146P 
a14xm MediaTek MT6833 Android 15(V)
```
############################################################################################################################################
1. How to Build

     (1) AOSP Kernel
         https://source.android.com/docs/setup/build/building-kernels
         $ repo init -u https://android.googlesource.com/kernel/manifest -b common-android14-6.1
         $ repo sync

     (2) Samsung Open Source
         https://opensource.samsung.com/uploadSearch?searchValue=Galaxy-A14-5g

   - get Toolchain
     get the proper toolchain packages from AOSP or Samsung Open Source or ETC.

     get the proper toolchain packages from AOSP or Samsung Open Source or ETC.
         copy the following list to the root directory
         - build/
         - external/
         - kernel/prebuilts/
         - prebuilts/

   - Set Build Environment and Export Target Config
      $ cd kernel
      $ python kernel_device_modules-6.6/scripts/gen_build_config.py
                                            --kernel-defconfig mediatek-bazel_defconfig
                                            --kernel-defconfig-overlays "mt6833_overlay.config S96901AA1.config S96901AA1_debug.config"
                                            --kernel-build-config-overlays ""
                                            -m user -o ../out/target/product/a14xm/obj/KERNEL_OBJ/build.config

      $ export DEVICE_MODULES_DIR="kernel_device_modules-6.6"
      $ export BUILD_CONFIG="../out/target/product/a14xm/obj/KERNEL_OBJ/build.config"
      $ export OUT_DIR="../out/target/product/a14xm/obj/KLEAF_OBJ"
      $ export DIST_DIR="../out/target/product/a14xm/obj/KLEAF_OBJ/dist"
      $ export DEFCONFIG_OVERLAYS="mt6833_overlay.config S96901AA1.config S96901AA1_debug.config"
      $ export PROJECT="mgk_64_k66"
      $ export MODE="user"

   - To Build
      $ ./kernel_device_modules-6.6/build.sh

2. Output Files
   - Kernel : out/target/product/a14xm/obj/KLEAF_OBJ/dist/kernel_device_modules-6.6/mgk_64_k66_kernel_aarch64.user/Image.gz
   - Module : out/target/product/a14xm/obj/KLEAF_OBJ/dist/*/*.ko
############################################################################################################################################
#
```
