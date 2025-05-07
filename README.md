# Crzgames_BuilderLib

Ce dépôt build les bibliothèques des dépendences de Crzgames_RC2DCore qui sont plutôt très longue et pas possible dans un CMakeLists.txt. <br />
Les bibliothèques : OpenSSL, ONNX Runtime. <br />
Build pour les plateformes / architecture : macOS (x64/arm64), Windows (x64/arm64), Linux (x64/arm64), Android (arm64-v8a / armeabi-v7a) et iOS device (arm64).

<br />

---

ONNX Runtime :
- macOS 10.12 et ultérieures -> issue concernant macOS 13.3 minimum : https://github.com/microsoft/onnxruntime/issues/21033
- iOS device >= 13.0 (vu que l'API SDL3 GPU demande minimum 13.0) 
