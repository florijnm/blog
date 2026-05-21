```
# Functie om de status af te drukken
function Print-Status {
    param (
        [string]$message
    )
    Write-Host "[$(Get-Date -Format 'yyyy-MM-dd HH:mm:ss')] $message" -ForegroundColor Cyan
}

# 1. Robocopy
Print-Status "Starten van Robocopy om bestanden te kopiëren..."
$robocopyCommand = 'robocopy "D:\Zettlekasten\posts" "C:\Users\Florijn\blog\content\posts" /mir'
Invoke-Expression $robocopyCommand
if ($LASTEXITCODE -eq 0) {
    Print-Status "Robocopy voltooid zonder fouten."
} else {
    Print-Status "Robocopy voltooid met fouten (code $LASTEXITCODE)."
}

# 2. Wijzig naar de juiste directory voor Hugo
Print-Status "Wijzigen naar de Hugo directory C:\Users\Florijn\blog..."
Set-Location -Path "C:\Users\Florijn\blog"

# 3. Start Hugo
Print-Status "Starten van Hugo..."
$hugoCommand = 'hugo'
Invoke-Expression $hugoCommand
if ($LASTEXITCODE -eq 0) {
    Print-Status "Hugo voltooid zonder fouten."
} else {
    Print-Status "Hugo voltooid met fouten (code $LASTEXITCODE)."
}

# 4. Git add . en commit met een custom bericht
Print-Status "Voer git add . uit en maak een commit met de datum en tijd als bericht..."
$commitMessage = "Update op $(Get-Date -Format 'yyyy-MM-dd HH:mm:ss')"
$gitAddCommand = 'git add .'
Invoke-Expression $gitAddCommand
$gitCommitCommand = "git commit -m `"$commitMessage`""
Invoke-Expression $gitCommitCommand
if ($LASTEXITCODE -eq 0) {
    Print-Status "Git commit voltooid met boodschap: $commitMessage"
} else {
    Print-Status "Git commit mislukt (code $LASTEXITCODE)."
}

# 5. Force push naar master
Print-Status "Force push naar master branch..."
$gitPushCommand = 'git push origin master --force'
Invoke-Expression $gitPushCommand
if ($LASTEXITCODE -eq 0) {
    Print-Status "Git push voltooid zonder fouten."
} else {
    Print-Status "Git push voltooid met fouten (code $LASTEXITCODE)."
}

# 6. Git subtree split
Print-Status "Starten van git subtree split..."
$gitSubtreeCommand = 'git subtree split --prefix public -b deploy'
Invoke-Expression $gitSubtreeCommand
if ($LASTEXITCODE -eq 0) {
    Print-Status "Git subtree split voltooid zonder fouten."
} else {
    Print-Status "Git subtree split voltooid met fouten (code $LASTEXITCODE)."
}

Print-Status "Starten van git push..."
$gitPushCommand = 'git push origin deploy:deploy --force'
Invoke-Expression $gitPushCommand
if ($LASTEXITCODE -eq 0) {
    Print-Status "Git push voltooid zonder fouten."
} else {
    Print-Status "Git push voltooid met fouten (code $LASTEXITCODE)."
}


Print-Status "Alle commando's zijn uitgevoerd."

# Wacht op de gebruiker om het script af te sluiten
Write-Host "Het script is voltooid. Druk op Enter om het script af te sluiten..."
$null = Read-Host
```