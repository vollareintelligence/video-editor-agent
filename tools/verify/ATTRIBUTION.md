# Atribuição

`probe-mp4.sh` e `contact-sheet.sh` são cópias de `tools/verify/` do repositório
https://github.com/iart-ai/motion-skills, commit 238dfc5.

Licença original: MIT, Copyright (c) 2026 iart.ai. Texto integral em `LICENSE-MIT-iart-ai.txt`.

Alteração: `probe-mp4.sh` ganhou `export LC_ALL=C` logo após `set -euo pipefail`. Em locale
pt_BR o `printf '%.2f'` rejeita o ponto decimal e o script saía com erro antes de conferir
o contrato (encontrado no Windows/Git Bash em 2026-10-25).
