# sources
Debian 11 open sources to refresh Desktop PC

## Latest mesa 22.3.3 source codes

**Enter to the mesa<version> folder and:**

```
meson configure
meson builddir/ --prefix="/projects/installers/" --pkg-config-path=/projects/installers/lib/x86_64-linux-gnu/pkgconfig,/projects/installers/share/pkgconfig -Degl=enabled -Degl-native-platform=wayland -Dgallium-nine=true -Dgallium-opencl=icd -Dgallium-va=true -Dgallium-vdpau=true -Dglx=dri
ninja -C builddir/ install
```

**Afterwards in gnome terminal export all neccessary variables:**

```
export LD_LIBRARY_PATH=/projects/installers/lib/x86_64-linux-gnu
export LIBGL_DRIVERS_PATH=/projects/installers/lib/x86_64-linux-gnu/dri
export VK_ICD_FILENAMES=/projects/installers/share/vulkan/icd.d/radeon_icd.x86_64.json
export D3D_MODULE_PATH=/projects/installers/lib/x86_64-linux-gnu/d3d/d3dadapter9.so.1
```

**And check:**
`vulkaninfo`
**or**
`glxinfo`

## Enjoy play newest Windows games with Direct X 12+!

