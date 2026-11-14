# Relatório Técnico — AC05: Materiais PBR e Texturização

**Aluno:** Vitor Sossai  
**Curso:** Ciência de Dados e Inteligência Artificial (CDIA) — IBMEC Barra  
**Software:** Blender 4.5 LTS  

---

## 1. Identificação dos Objetos e Materiais
* **`OBJ_Predio_IbmecBarra`**: Recebeu o material `MAT_Metal_Predio_PBR` (superfície metálica polida com reflexos direcionados e variação de rugosidade).
* **Coleção `03_Cenario_Auxiliar` (Piso e Canteiros)**: Recebeu o material `MAT_Concreto_Cenario_PBR` (pavimentação externa estruturada com mapas PBR completos).
* **`01_Palavra_Ibmec`**: Recebeu o material `MAT_Ibmec_Identidade_PBR` (cor sólida institucional com acabamento acetinado de baixa rugosidade, preservando integralmente a identidade visual e legibilidade).

## 2. Propriedades Principais dos Materiais
* **Metal do Prédio**: `Metallic = 1.0`, `Roughness = 0.25`.
* **Concreto do Cenário**: `Metallic = 0.0` (dielétrico), `Roughness` controlada por mapa de dados dedicado.
* **Logotipo Ibmec**: `Metallic = 0.05`, `Roughness = 0.15`.

## 3. Configuração dos Mapas e Conexões (Shader Editor)
* **Base Color / Albedo**: Configurado no espaço de cor **sRGB** e conectado diretamente à entrada correspondente do *Principled BSDF*.
* **Roughness**: Configurado estritamente como **Non-Color** para evitar distorções de gama na leitura de dados de brilho.
* **Normal Map**: Imagem de relevo configurada como **Non-Color**, passando por um nó intermediário *Normal Map* (*Tangent Space*) antes de alimentar a entrada `Normal` do shader.

## 4. Método de Mapeamento UV
* Utilizou-se a ferramenta **Smart UV Project** (`angle_limit = 1.15`, *island margin*) em malhas complexas e no piso para gerar ilhas limpas e evitar distorções visuais ou repetições excessivas (*tiling*).

## 5. Origem dos Recursos Externos
* Texturas e mapas de suporte estruturados com base em referências PBR de alta fidelidade (compatíveis com padrões CC0).

## 6. Influência da Iluminação na Resposta PBR
* A luz principal tipo *Area* incidiu de forma dinâmica sobre os mapas de rugosidade e relevo, evidenciando o realismo tátil das superfícies do cenário sem gerar estouros visuais que comprometessem o foco central na palavra Ibmec.
