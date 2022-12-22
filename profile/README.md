# vkngwrapper

Vkngwrapper (proununced "Viking Wrapper") is a handwritten cgo wrapper for the Vulkan graphics and compute API.
 The goal is to produce fast, easy-to-use, low-go-allocation, and idiomatic Go code to communicate with your graphics
 card and enable games and other graphical applications. Vkngwrapper currently supports core versions 1.0-1.2 
 via the https://github.com/vkngwrapper/core repository, as well as many extensions via the https://github.com/vkngwrapper/extensions repository.

Under the hood, Vkngwrapper uses https://github.com/cannibalvox/cgoparam to avoid calling `C.Malloc` and
`C.Free` while still avoiding the cost of a deep cgocheck on Go memory. This allows you to save precious
nanoseconds (or sometimes microseconds!) on your cgo overhead.

Vkngwrapper is also heavily-tested. The marshalling and unmarshalling layer has high test coverage, giving the
core library 84.5% test coverage and the extensions library 87.9% test coverage. While this coverage is not
perfect, Vulkan has an extremely large API surface, and these tests ensure that there is no obviously-busted
functionality. Additionally, the entire API is mockable (and pre-generated gomocks are provided), allowing you
to test your own code with ease.

Lastly, vkngwrapper has a solid and still-growing base of examples, built from Go ports of existing Vulkan
examples.  Several key samples from https://github.com/LunarG/VulkanSamples have are included in
[our example repository](https://github.com/vkngwrapper/examples), as well as a full port of
[the Vulkan tutorial](https://vulkan-tutorial.com), which can be followed step by step at
https://github.com/vkngwrapper/vulkan-tutorial

For more information about how to use vkngwrapper, check out [the core repository](https://github.com/vkngwrapper/core)!

## Roadmap

- [X] Vulkan Wrapper core 1.0-1.2
- [x] Fast, zero allocation 3d math library with ~SIMD support~ ([Why not SIMD?](https://github.com/vkngwrapper/math#why-not-simd))
- [ ] Pure go port of [VMA](https://github.com/GPUOpen-LibrariesAndSDKs/VulkanMemoryAllocator)
- [ ] Pure go port of Quake 2
- [ ] Vulkan Wrapper core 1.3
- [ ] ~NEON/SVE support in 3d math library~ ([Why not SIMD?](https://github.com/vkngwrapper/math#why-not-simd))
- [ ] Fyne and/or GioUI Integration
- [ ] Port many [Vulkan Samples](https://github.com/KhronosGroup/Vulkan-Samples), using Fyne or GioUI in place of DearImgui
 
