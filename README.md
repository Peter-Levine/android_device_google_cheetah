TWRP Device tree for the Google Pixel 7 Pro (android 13)
=================================================

| Basic                   | Spec Sheet                                                                                                                     |
| -----------------------:|:------------------------------------------------------------------------------------------------------------------------------ |
| CPU                     | Octa-core (2x2.85 GHz Cortex-X1 & 2x2.35 GHz Cortex-A78 & 4x1.80 GHz Cortex-A55)                                                |
| Chipset                  | Google Tensor G2                                                         |
| GPU                      | Mali-G710 MP7                                                                         |
| Memory                   | 8/12 GB RAM                                                           |
| Shipped Android Version  | 13.0                                                         |
| Storage                  | 128/256/512 GB                                     |
| Battery                  | Non-removable Li-Ion 5000 mAh battery                        |
| Display                  | 1440 x 3120 pixels, 19.5:9 ratio (~512 ppi density)                                    |
| Camera (Back) Wide       | 50 MP, f/1.9, 25mm, 1/1.31", 1.2µm, multi-directional PDAF, Laser AF, OIS
| Camera (Back) Telephoto  | 48 MP, f/3.5, 120mm, 1/2.55", 0.7µm, multi-directional PDAF, OIS, 5x optical zoom
| Camera (Back) Ultrawide  | 12 MP, f/2.2, 126˚, 1/2.9", 1.25µm, AF                          |
| Camera (Front)           | 10.8 MP, f/2.2, 21mm (ultrawide), 1/3.1", 1.22µm                                                                                     |

## How-to compile it:
# Init repo
$ repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1

# Sync
$ repo sync --no-repo-verify -c --force-sync --no-clone-bundle --no-tags --optimized-fetch --prune -j`nproc`

# Clone common tree repo
$ git clone https://github.com/Peter-Levine/android_device_google_gs201 device/google/gs201-common

# Clone tree
$ git clone  https://github.com/Peter-Levine/android_device_google_cheetah device/google/cheetah

# Build
$ source build/envsetup.sh; export ALLOW_MISSING_DEPENDENCIES=true; lunch twrp_cheetah-eng; mka recoveryimage

