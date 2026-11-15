# IgaraPost
garaPost is an environmental social network by Vento Norte UEA for NASA Space Apps. It connects Amazon communities' geolocated reports of smoke, fires and floods with satellite data, interactive maps and experimental NISAR image comparisons, making Earth observation more accessible and supporting citizen science.
<div align="center"> <img src="app/public/igarapost-logo.png" alt="Logo do IgaraPost" width="120" />
Créditos e agradecimentos

IgaraPost · Equipe Vento Norte UEA · NASA Space Apps Challenge 2026 · desafio Dancing with the SARs

</div>

O IgaraPost foi criado pela equipe Vento Norte, da Universidade do Estado do Amazonas (UEA). Para chegar até aqui, usamos bibliotecas open source, dados abertos de agências espaciais e científicas e serviços de terceiros. Esta página reconhece cada um deles e deixa claro o que foi desenvolvido pela equipe.

Sumário
Desenvolvido pela equipe Vento Norte
Dados e serviços
Bibliotecas incluídas no app
Ferramentas de desenvolvimento
Processamento de dados em Python
Tipografia, ícones e imagens
Uso de inteligência artificial
🚀 Desenvolvido pela equipe Vento Norte

O código, as telas, os textos e as artes abaixo foram criados para o IgaraPost e não têm autoria externa. Eles usam as bibliotecas listadas nas próximas seções, mas a lógica, o design e o conteúdo são da equipe.

Parte	O que inclui
App (app/src/)	Todas as telas (Feed, Mapa, Relatar, Perfil, Explorador NISAR, Como usar, Sobre), componentes, armazenamento no aparelho, fila de sincronização e conexão com o Supabase
Provedor SARS (app/src/sars/)	Camadas globais, tempo real, regiões e a conferência "fora do radar" dos relatos
Tradução (app/src/i18n/)	Sistema de idiomas e dicionários da interface
Banco de dados (supabase/)	Tabelas, regras de segurança (RLS), gatilhos, fotos e moderação
Servidor (server/)	Servidor das versões até a 8, em Node.js puro, mais Dockerfile e render.yaml
Pipeline de dados (data-pipeline/)	Scripts de download, recorte e processamento dos dados do INPE, Cemaden, OpenStreetMap e NISAR
Testes (app/tests/)	Testes de ponta a ponta, Supabase simulado e testes de idiomas
Android (app/android/)	Personalização do projeto gerado pelo Capacitor: pacote, versões, assinatura, ícones e telas de abertura
Identidade visual	Logo do IgaraPost, logo da Vento Norte UEA, ícones do app, foto da equipe e arte de fundo "Outro"
Documentação	README.md e a pasta docs/
🛰️ Dados e serviços

O IgaraPost só existe graças a dados abertos. Agradecemos às instituições que os mantêm.

Fonte	Responsável	Uso no IgaraPost
NASA GIBS	NASA EOSDIS / ESDIS	Camadas de fumaça (MODIS AOD), enchentes (MODIS Flood), imagem do dia (VIIRS) e mapa de fundo Blue Marble Next Generation
NASA FIRMS	NASA LANCE	Focos de fogo ativo (VIIRS NOAA-20 e Suomi NPP)
OPERA DSWx-S1	NASA/JPL	Água superficial detectada por radar. Contém dados Copernicus Sentinel modificados (ESA).
NISAR, via ASF DAAC	NASA/JPL e ISRO	Explorador NISAR no entorno de Manaus
Programa Queimadas	INPE	Focos de calor no Brasil e atualização em tempo real
Alerta Secas	Cemaden/MCTI	Limites dos municípios
OpenStreetMap	© colaboradores do OpenStreetMap (ODbL)	Mapa de ruas, localidades, rios e vias
MyMemory	Translated srl	Tradução automática dos relatos
Supabase	Supabase Inc.	Contas, relatos, comentários, fotos e moderação
Google Maps Platform (opcional)	Google	Fundos "Google Satélite" e "Google Mapa", quando há chave configurada
📦 Bibliotecas incluídas no app

Estas bibliotecas vão dentro do APK. Todas são open source, e os avisos de copyright seguem as licenças de cada uma.

Biblioteca	Versão	Autoria	Licença
React e React DOM	18.3.1	Meta Platforms, Inc. e colaboradores	MIT
Leaflet	1.9.4	Volodymyr Agafonkin e colaboradores	BSD-2-Clause
Capacitor (core e android)	6.2.0	Ionic e colaboradores	MIT
Apache Cordova Android	10.1.1	Apache Software Foundation	Apache 2.0
AndroidX / Jetpack	várias	Google / Android Open Source Project	Apache 2.0
Kotlin e kotlinx.coroutines	1.6.4 (coroutines)	JetBrains e colaboradores	Apache 2.0
<details> <summary><b>Módulos AndroidX incluídos</b></summary> <br>
Módulo	Versão
appcompat · appcompat-resources	1.6.1
core · core-ktx	1.12.0
core-splashscreen	1.0.1
coordinatorlayout	1.2.0
activity	1.8.0
fragment	1.6.2
webkit	1.9.0
emoji2 · emoji2-views-helper	1.2.0
savedstate	1.2.1
startup-runtime	1.1.1
profileinstaller	1.3.0
annotation-experimental	1.3.0
lifecycle, arch-core, loader, viewpager, drawerlayout, customview, cursoradapter, interpolator, vectordrawable, versionedparcelable, tracing	dependências do AndroidX
</details>
🛠️ Ferramentas de desenvolvimento

Estas ferramentas foram usadas para construir e testar o projeto e não vão dentro do APK.

Ferramenta	Autoria	Licença
Vite 5.4, com esbuild e Rollup	Evan You, Evan Wallace, Rich Harris e colaboradores	MIT
TypeScript 5.5	Microsoft	Apache 2.0
DefinitelyTyped (@types/react, @types/leaflet)	Comunidade	MIT
Capacitor CLI 6.2	Ionic	MIT
Gradle e Android Gradle Plugin 8.2	Gradle Inc. e Google	Apache 2.0
Playwright	Microsoft	Apache 2.0
tsx	Hiroki Osame e colaboradores	MIT
Node.js 22	OpenJS Foundation	MIT
PostgreSQL (via Supabase)	PostgreSQL Global Development Group	PostgreSQL License
🐍 Processamento de dados em Python

Bibliotecas usadas em data-pipeline/ para baixar e preparar os dados de satélite.

Biblioteca	Autoria	Licença
NumPy	NumPy Developers	BSD-3-Clause
SciPy	SciPy Developers	BSD-3-Clause
Pillow	Jeffrey A. Clark e colaboradores	MIT-CMU
h5py	Andrew Collette e colaboradores	BSD-3-Clause
Rasterio	Mapbox e colaboradores	BSD-3-Clause
pyproj	pyproj contributors	MIT
Shapely	Sean Gillies e colaboradores	BSD-3-Clause
earthaccess	NSIDC e comunidade earthaccess	MIT
🎨 Tipografia, ícones e imagens

Fontes, carregadas pelo Google Fonts e todas sob a SIL Open Font License 1.1:

Bricolage Grotesque, de Mathieu Triay
Inter, de Rasmus Andersson
IBM Plex Mono, da IBM

Ícones: desenhados pela equipe em SVG. O ícone de sino vem do Lucide (licença ISC).

Imagens de fundo das publicações:

Imagem	Autoria
Queimada (brigadista em incêndio)	[autor e veículo a confirmar]
Fumaça (Teatro Amazonas encoberto)	[autor e veículo a confirmar]
Enchente (rua alagada em Manaus)	[autor e veículo a confirmar]
Outro (arte do IgaraPost)	Equipe Vento Norte

Mapa de fundo offline: NASA Blue Marble Next Generation, via GIBS.

🤖 Uso de inteligência artificial

Seguindo as regras do NASA Space Apps Challenge, declaramos que o IgaraPost foi desenvolvido pela equipe Vento Norte UEA com o auxílio da IA Claude (Anthropic) na escrita, revisão e teste do código e dos scripts de processamento de dados. As decisões de projeto, a identidade visual e a validação final foram da equipe.

<div align="center">

Feito em Manaus, Amazonas, pela Equipe Vento Norte · UEA 🌳🛶

</div>
