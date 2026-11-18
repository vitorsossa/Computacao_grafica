Relatório Técnico — AP2: Ibmec em 15 Segundos

Autor: Vitor Sossai

Disciplina: Computação Gráfica / Modelagem 3D

Instituição: Ibmec Barra

Ferramenta: Blender 4.5 LTS

1. Título, Conceito e Resumo da Sequência

Título da Peça: Engenharia do Futuro: Ibmec em 15 Segundos

Conceito: A peça audiovisual representa a integração entre a solidez arquitetônica, a inovação tecnológica e a identidade institucional do Ibmec Barra. A cena posiciona o edifício principal (OBJ_Predio_IbmecBarra) como marco estrutural ao fundo, acompanhado pela palavra institucional (mesh_word_ibmec) em destaque central e por três objetos autorais de sustentação e composição (pedestal_ibmec, pedestal_ibmec001, pedestal_ibmec002), integrados a um cenário urbano (03_Cenario_Auxiliar).

Resumo da Sequência: Ao longo de 15 segundos (360 quadros a 24 fps), a narrativa visual inicia com um plano aberto revelando o ambiente arquitetônico enquanto a palavra Ibmec emerge suavemente até sua posição de destaque. Na sequência, a câmera realiza um movimento orbital fluido que valoriza os reflexos metálicos da fachada e os pedestais institucionais, encerrando em um enquadramento frontal equilibrado que garante total legibilidade da marca.

2. Descrição dos Momentos / Planos e Ações Animadas

A sequência foi estruturada em três atos contínuos para manter o ritmo visual e a clareza narrativa:

Ato / Plano

Intervalo (Frames / Tempo)

Enquadramento e Movimento de Câmera

Ação dos Elementos na Cena

Ato 1: Apresentação

Frames 1 a 75 (0,0s – 3,1s)

Plano geral frontal (Location: (0, -14, 4.5)), estabilizando a visão da praça e da fachada.

A palavra mesh_word_ibmec realiza movimento vertical de ascensão no eixo Z (de -2.5 m até 0.0 m), emergindo no centro da composição.

Ato 2: Desenvolvimento

Frames 76 a 240 (3,1s – 10,0s)

Movimento panorâmico e orbital suave em direção à diagonal direita (Location: (3.5, -11, 5.0)), explorando profundidade e perspectiva.

A câmera revela a tridimensionalidade dos três pedestais autorais (pedestal_ibmec e variantes) e a interação da luz com a estrutura metálica do edifício.

Ato 3: Encerramento

Frames 241 a 360 (10,0s – 15,0s)

Aproximação frontal centralizada (Location: (0, -9, 4.0)), fechando em plano médio de alto impacto.

Estabilização completa da cena com a marca Ibmec nítida, centralizada e em pleno contraste com o edifício e os pedestais.

3. Propriedades Animadas e Decisões de Timing / Interpolação

Propriedades Animadas:

Câmera Principal (Camera): Propriedades location (eixos X, Y, Z) e rotation_euler (eixos X, Z), chaveadas nos frames 1, 180 e 360.

Logotipo Institucional (mesh_word_ibmec): Propriedade location (eixo Z), chaveada nos frames 1 e 75.

Decisões de Timing e Interpolação:

A animação foi configurada em 24 fps totalizando 360 frames (15 segundos exatos).

No Graph Editor, utilizou-se interpolação Bézier com atenuação suave (Ease In / Ease Out) nas extremidades dos keyframes. Essa escolha evita paradas bruscas na movimentação da câmera e confere peso e fluidez à elevação da palavra Ibmec nos primeiros 3 segundos, mantendo a legibilidade constante sem trepidações ou colisões visuais.

4. Configuração Geral de Iluminação e Renderização

Iluminação:

Configurada com base nos estudos da AC04 para valorizar o relevo das superfícies PBR e a leitura da marca, combinando luz direcional principal (simulando iluminação solar arquitetônica) com luzes de preenchimento suaves e iluminação ambiente controlada no World (tonalidade azul-noturna profunda para gerar contraste com os materiais metálicos).

Configurações de Renderização e Exportação:

Motor de Renderização: Eevee (Blender 4.5 LTS), otimizado para reflexos metálicos em tempo real sem ruído excessivo.

Resolução e Taxa de Quadros: 1920 x 1080 (Full HD, 100%) a 24 fps (Frames 1 a 360).

Formato de Saída: FFmpeg Video, contêiner MPEG-4 (.mp4), codec de vídeo H.264 com qualidade HIGH.

5. Descrição dos Materiais e Texturas (AC05)

Os materiais desenvolvidos na AC05 foram reaproveitados e calibrados para responder adequadamente à movimentação da câmera e à iluminação final, utilizando o shader Principled BSDF (baseado em princípios físicos):

Palavra Ibmec (MAT_Ibmec_Identidade_PBR): Aplicado em mesh_word_ibmec. Configurado com azul institucional sólido (Base Color azul intenso), baixa metalicidade (0.05) e acabamento acetinado (Roughness: 0.12) para garantir legibilidade e destaque visual sob qualquer ângulo.

Edifício Principal (MAT_Metal_Predio_PBR): Aplicado em OBJ_Predio_IbmecBarra. Configurado como superfície metálica (Metallic: 1.0) em tom azul-aço arquitetônico com rugosidade baixa (Roughness: 0.14), gerando reflexos dinâmicos do ambiente e dos elementos próximos durante o movimento da câmera.

Três Objetos Autorais (MAT_Pedestal_Azul_Metalico): Aplicado nos objetos pedestal_ibmec, pedestal_ibmec001 e pedestal_ibmec002. Acabamento em azul metálico (Metallic: 0.90, Roughness: 0.22) que harmoniza os pedestais com a identidade da marca e a fachada do prédio.

Piso e Cenário Auxiliar (MAT_Concreto_Cenario_PBR e MAT_Vegetacao_Canteiro_PBR): Texturas PBR de concreto aplicadas no piso da coleção 03_Cenario_Auxiliar, com mapas de rugosidade (Roughness) e relevo (Normal Map) devidamente configurados no espaço de cor Non-Color e escala UV ajustada.

6. Desafios Encontrados e Soluções Adotadas

Desafio 1 — Cintilação (Flickering / Z-fighting) na textura do piso durante o movimento da câmera:

Solução: Foi realizada a limpeza de vértices sobrepostos (Merge by Distance), aplicado um microdeslocamento vertical (-0.003 m) na malha do piso para eliminar coplanaridade com os canteiros, ajustado o espaço de cor dos mapas de dados para Non-Color e reduzida a repetição (Tiling) no nó Mapping de 4.0 para 1.5, suavizando a força do Normal Map para 0.45.

Desafio 2 — Sincronização visual entre Viewport (Layout) e Render:

Solução: Padronização da propriedade diffuse_color de todos os materiais e configuração da viewport para exibição de materiais e iluminação de cena, assegurando fidelidade visual durante os testes de animação.

Desafio 3 — Garantia de portabilidade das texturas:

Solução: Todos os mapas externos foram empacotados diretamente no arquivo .blend (File > External Data > Pack Resources) para evitar perda de vínculos na abertura em outros computadores do laboratório.

7. Fontes e Licenças de Recursos Externos Utilizados

Software de Modelagem, Animação e Renderização: Blender 4.5 LTS — Licença GNU General Public License (GPL v3).

Modelagem 3D (Edifício Ibmec Barra, Logotipo 3D, Pedestais Autorais e Cenário): Autoria própria desenvolvida ao longo das etapas AP1, AC04, AC05 e AP2.

Texturas PBR (Concreto Urbano): Recursos de domínio público / Licença CC0 (Poly Haven / ambientCG), devidamente empacotados no arquivo AP2_VitorSossai.blend.
