# WiseFi docker

Fazer download do Inno Extract (https://constexpr.org/innoextract/)

Extrair arquivos do instalador do WiseFi

	innoextract "Instalador Wisefi Web.exe"

Copiar pastas **web** e **captiveportal** que estão dentro da pasta **app** para estar pasta

Construir imagens do docker (controller e captive portal)

	docker-compose build

Iniciar o WiseFi

	docker-compose up -d

Acessar através dá pagina web http://localhost:8000/
