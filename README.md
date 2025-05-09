# Crzgames_BuilderLib

Ce dépôt build les bibliothèques des dépendences de Crzgames_RC2DCore qui sont plutôt très longue et pas possible dans un CMakeLists.txt. <br />
Les bibliothèques : OpenSSL, ONNX Runtime. <br />
Build pour les plateformes / architecture : macOS (x64/arm64), Windows (x64/arm64), Linux (x64/arm64), Android (arm64-v8a / armeabi-v7a) et iOS device (arm64).

<br />

---

ONNX Runtime - Apple (iOS / macOS) :
- macOS x64/arm64 fat lib possible.
- macOS 10.12 et ultérieures (c'est écrit sur la doc mais c'est faux) -> Il faut target la version macOS >= 13.4 et avec un sdk >= 14.4, issue concernant concernant cela : https://github.com/microsoft/onnxruntime/issues/21033
- iOS 13.0 et ultérieurs (vu que le flag --use_coreml demande iOS 13.0+)
- Utiliser CMake 3.28 (minimum demandé par ONNX Runtime) à 3.31 (après cette version c'est CMake version 4.x.x, et n'ai pas compatible avec le flag : --use_coreml)

ONNX Runtime - Windows :
- Windows x64/arm64 possible.
- Direct ML compatible que : x64 mais pas arm64, utilise Direct3D12.
- Windows x64 : Fallback sur XNN si pas Direct3D12 (Execution Providers)
- Windows arm64 : XNN obligatoirement (Execution Providers)

ONNX Runtime - Linux :
- Linux x64/arm64 possible.
- XNN (Execution Providers)

ONNX Runtime - Android :
- Android arm64-v8a/armeabi-v7a possible.
- NNAPI (Execution Providers) compatible que à partir de : Android 8.1+ (API 27+).
