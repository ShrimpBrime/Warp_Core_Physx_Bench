Warp Core Bench
CPU and GPU physics benchmarking inside a sci-fi reactor.

Warp Core Bench combines CPU, CUDA, and Vulkan benchmark paths with a customizable reactor viewer, repeated-run scoring, and local result reports. Run a benchmark, inspect its consistency, and compare results from matching workloads and protocols.

Developer: ShrimpBrime · Warp9-Systems™

<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144431_093" src="https://github.com/user-attachments/assets/e2ca675d-abd8-4eda-ba2c-3820e920cab1" />
<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144610_898" src="https://github.com/user-attachments/assets/16980da1-d83c-4ea8-9763-6726ac115ae6" />
<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144622_722" src="https://github.com/user-attachments/assets/8c3cc577-47a5-4dce-80af-56cb08a28017" />
<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144639_684" src="https://github.com/user-attachments/assets/fba7e391-08f3-4433-89db-6eebd47aefae" />
<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144631_889" src="https://github.com/user-attachments/assets/f55256c9-3f01-4003-a5b7-96ccde3cefb4" />
<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144645_131" src="https://github.com/user-attachments/assets/b26bc862-f266-461c-a63d-c35e5ace7690" />
<img width="1920" height="1009" alt="WarpCoreBench_v0 99h_20261030_144715_673" src="https://github.com/user-attachments/assets/5a9fddc5-1d59-4057-9c78-ea0119b756f0" />



Backend	Workload	Hardware
CPU	NVIDIA PhysX CPU simulation	Supported x64 CPUs, independent of GPU vendor
CUDA	PhysX GPU workloads, including provisional BOX150K scoring	Compatible NVIDIA GPU and driver
Vulkan	Compute-based sphere simulation with provisional 8K scoring	Compatible Vulkan compute GPU and driver


Each path has its own workload and scoring method. Compare results within the same backend, protocol, and run profile. CPU PhysX, CUDA BOX150K, and Vulkan sphere scores are separate measurements.
Features
- Repeated-run scoring: Review aggregate scores alongside individual results and repeatability information.
- Visible run progress: CPU and GPU benchmark indicators remain available while the Actions controls are expanded.
- Measurement isolation: Benchmark work runs in worker processes; the reactor viewer pauses its simulation and holds its 3D presentation during measurement.
- Experimentation lab: Explore research workloads and validation tools separately from the main benchmark controls.
- Customizable reactor: Chrome and colored particles, pulse controls, and sci-fi room visuals.
- Local reports and exports: Keep results for comparison, troubleshooting, and sharing with testers.
- App screenshots: Capture the interface directly from the application.
- Portable distribution: The release packaging supports one executable containing the application, workers, assets, and required runtime files.
Download and run
1. Download the tester release from this repository's Releases section.
2. Extract the download and launch WarpCoreBench.exe.
3. Open Benchmarks, select a supported backend, and start a run.
4. Review the score, individual passes, and repeatability result.
The portable application requires no installer or administrator privileges. Testers do not need Visual Studio, CMake, the PhysX SDK, CUDA Toolkit, or Vulkan SDK.
Requirements
- Windows 10 or Windows 11, 64-bit.
- A graphics driver capable of running the reactor viewer.
- A compatible NVIDIA GPU and driver for CUDA benchmarks.
- A compatible Vulkan compute device and driver for Vulkan benchmarks.
Optional Vulkan validation-layer checks in the experimentation lab require the validation layer to be installed separately. Ordinary Vulkan benchmark runs do not require it.
Scoring and consistency
Warp Core Bench is under active development. Current GPU scores are provisional, and leaderboard submission is disabled.

The Vulkan 8K provisional profile runs three fresh worker processes back to back, measures each run for approximately ten seconds, and uses the median scene steps per second as its score. Its repeatability limit is 5%, calculated as:
Spread (%) = 100 × (maximum run rate − minimum run rate) / median run rate
Incomplete, invalid, mismatched, or excessive-spread sessions withhold the Vulkan score while retaining reports for investigation.

For useful comparisons, keep the application version, protocol, run profile, and system configuration consistent. Record driver versions and tuning settings when sharing results. A score describes performance in its specific workload; it is not a general gaming-performance or system-stability rating.
Help test it
Try three benchmark sessions back to back and share the reports. We are especially interested in:
- Repeatability across sessions and different hardware.
- CPU, CUDA, and Vulkan compatibility.
- Cancellation, interrupted runs, and restarting the app.
- Incorrect progress, missing results, or scores that should have been withheld.
- Interface layout, screenshot capture, and result exports.
For a bug report, include the application version, CPU and GPU models, driver version, benchmark settings, relevant reports, and steps to reproduce the issue. Screenshots are welcome.
Local data and portable operation
Results are stored under:
%LOCALAPPDATA%\WarpCoreBench
Benchmark reports are not automatically uploaded.

The single-executable package extracts its components into a fresh per-user runtime folder, verifies their hashes, and retains file locks while the main application runs. Normal exit removes that launch's extracted files; saved results remain available. A forced termination can leave an extraction folder behind.

For taskbar pinning, create or pin a shortcut to the outer WarpCoreBench.exe, rather than the running application inside its temporary extraction folder.
Building from source
Use START_HERE_BUILD_AND_RUN.cmd for the development build, or BUILD_AND_SIGN.cmd for the complete signed portable tester package.

The developer build requires Visual Studio 2022 C++ build tools, CMake, and a matching compiled PhysX SDK. The complete tester package requires the GPU-enabled PhysX SDK and Vulkan worker. Its signing step uses a configured Azure signing account and verifies timestamped signatures before publishing release output.

The signed packaging workflow produces:
artifacts\publish\WarpCoreBench.exe
artifacts\WarpCoreBench_v0.99h_TESTERS.zip
Release packaging includes SHA-256 files. Check the executable's Digital Signatures tab to verify the published binary's signature. Code signing identifies the publisher and protects file integrity; it does not certify benchmark accuracy or competitive anti-cheat protection.
Third-party components
Built with NVIDIA PhysX, raylib, and Vulkan headers. Applicable licenses and notices accompany the packaged application. Product and technology names belong to their respective owners.
