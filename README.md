# Crzgames_BuilderLib

Ce dépôt contient les runner GitHub Actions auto-hébergé utilisé pour builder les bibliothèques des dépendences de CrzGames (ONNX Runtime, OpenSSL, SDL_ShaderCross, etc.) sur **Windows ARM64** et **Linux ARM64**.

---

## 🖥️ Installation du runner GitHub Actions – Windows ARM64

1. Rendez-vous dans **Settings > Actions > Runners** sur GitHub.
2. Suivez les instructions fournies par GitHub.
3. Lancez ensuite le runner manuellement avec :
   ```cmd
   .\run.cmd
   ``
4. Suivez les étapes lors du premier lancement.

---

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

3. Appuyez sur `Win + R`, tapez `shell:startup` puis **Clique droit, créer un raccourci vers `launch-runner.vbs`** dans ce dossier.
