# Crzgames_BuilderLib

Ce dépôt build les bibliothèques des dépendences de Crzgames_RC2DCore qui sont plutôt très longue et pas possible dans un CMakeLists.txt. <br />
Les bibliothèques : OpenSSL, ONNX Runtime. <br />
Build pour les plateformes / architecture : macOS (x64/arm64), Windows (x64/arm64), Linux (x64/arm64), Android (arm64-v8a / armeabi-v7a) et iOS device (arm64).

<br />

---

<br />

## 🖥️ Installation du runner Github Actions – Windows ARM64

1. Rendez-vous dans **Settings > Actions > Runners** sur GitHub.
2. Suivez les instructions fournies par GitHub pour installer le runner sur notre machine.
3. Lancer ensuite la dernière étape pour lancer le runner manuellement avec :
   ```cmd
   .\run.cmd
   ```

    > Suivez les étapes lors du premier lancement.

<br />

---

<br />

## ⚙️ Lancement automatique du runner auto heberger pour Windows ARM64 (au démarrage)

### Étapes :

1. Créez un fichier `start-runner-hidden.ps1` dans `C:\actions-runner` :
   ```powershell
   Start-Process -WindowStyle Hidden -FilePath "C:\actions-runner\run.cmd"
   ```

2. Créez un fichier `launch-runner.vbs` dans `C:\actions-runner` :
   ```vbscript
   Set WshShell = CreateObject("WScript.Shell")
   WshShell.Run "powershell.exe -ExecutionPolicy Bypass -File C:\actions-runner\start-runner-hidden.ps1", 0, False
   ```

   > Le `0` signifie que le script sera **totalement caché**, sans fenêtre ni terminal.

2. Appuyez sur `Win + R`, tapez `shell:startup` puis **ENTRER**, puis **Clique droit, créer un raccourci vers `launch-runner.vbs`** dans ce dossier.


ONNX Runtime :
- macOS 10.12 et ultérieures -> issue concernant macOS 13.3 minimum : https://github.com/microsoft/onnxruntime/issues/21033
- iOS device >= 13.0 (vu que l'API SDL3 GPU demande minimum 13.0) 
