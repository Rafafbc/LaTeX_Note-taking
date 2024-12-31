## Usado para copiar um arquivo de um repositório no GitHub
```powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/SeniorMars/dotfiles/main/latex_template/template.tex" -OutFile "./template_test.tex"
```

### No caso de querer copiar mais de um arquivo
```powershell
# List of raw file URLs
$urls = @(
    "https://raw.githubusercontent.com/SeniorMars/dotfiles/main/latex_template/template1.tex",
    "https://raw.githubusercontent.com/SeniorMars/dotfiles/main/latex_template/template2.tex"
)

# Loop through the URLs and download each file
foreach ($url in $urls) {
    $filename = Split-Path -Leaf $url
    Invoke-WebRequest -Uri $url -OutFile "./$filename"
}
```