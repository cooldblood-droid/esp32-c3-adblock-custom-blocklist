# Lista personalizada do ESP32-C3 AdBlock

Este repositório monta um arquivo blocklist.bin no formato que o firmware do ESP32-C3 aceita e publica o arquivo em uma release do GitHub.

## Fontes incluídas

- StevenBlack hosts (base de anúncios e malware)
- HaGeZi Multi Pro, formato de domínios
- HaGeZi Native LG webOS, formato de domínios
- EasyList Portuguese; o compilador só aproveita regras por domínio que podem ser expressas por DNS
- Domínios portugueses/brasileiros adicionais mantidos em data/easylistportuguese_dns.txt

O bloqueio por DNS não remove elementos visuais da página nem regras que dependam de URL/caminho. O compilador ignora essas regras do EasyList.

## Publicação e atualização

O GitHub Actions recompila diariamente às 04:27 UTC e também pode ser iniciado manualmente. Só publica quando todas as fontes baixam e a lista fica entre 200 mil domínios e 1,3 MB; se uma fonte falhar ou o arquivo exceder esse limite, a release anterior continua disponível.

Depois de publicar este repositório como público e executar a ação uma vez, configure na placa:

- URL: https://github.com/cooldblood-droid/esp32-c3-adblock-custom-blocklist/releases/download/blocklist/blocklist.bin
- Intervalo: 24 horas

Este será o endereço do repositório. A placa busca o bin diariamente; não coloque os links txt do HaGeZi diretamente no painel.

## Licença

O compilador foi copiado do projeto esp32-c3-adblock e permanece sob a licença MIT incluída neste repositório. Cada lista mantém os termos de seu respectivo mantenedor.