# Crzgames_BuilderLib

Runner Github Actions - Windows ARM64
1. Suivre les étapes que demande Github pour un runner auto heberger pour Windows ARM64.
2. Lancer en dernier : ./run.cmd, suivre les étaper demandé.
3. Pour lancer automatiquement le runner si l'ordinateur à redémarrer ou était eteint, en arrière plan completement caché :
   1. Crée un fichier start-runner-hidden.ps1 dans C:\actions-runner :
    Start-Process -WindowStyle Hidden -FilePath "C:\actions-runner\run.cmd"
  2. Crée un fichier launch-runner.vbs dans C:\actions-runner :
  Set WshShell = CreateObject("WScript.Shell")
  WshShell.Run "powershell.exe -ExecutionPolicy Bypass -File C:\actions-runner\start-runner-hidden.ps1", 0, False

  Le 0 signifie complètement caché, pas même minimisé.
