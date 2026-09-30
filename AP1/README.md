cat << 'EOF' > AP1/README.md
# AP1 - Modelagem e Conceito 3D: A Engenharia do Futuro

**Aluno:** Vitor Sossai  
**Instituição:** IBMEC Barra  
**Curso:** CDIA  
**Software:** Blender 4.5 LTS  

---

## 📌 Visão Geral da Maquete
O projeto apresenta a palavra **Ibmec** em destaque no centro da maquete, sustentada por um pedestal elevado. Ao fundo, encontra-se o **Edifício Ibmec Barra** recuado para criar profundidade, acompanhado por uma **Ponte Estaiada** com pilares e cabos de sustentação, canteiros laterais com vegetação estilizada e postes de iluminação.

---

## 📸 Capturas de Tela da Cena

| 1. Visão da Câmera Principal | 2. Destaque Ibmec + Prédio Barra |
| :---: | :---: |
| ![Câmera Principal](images/Imagem1_CamPrincipal.png) | ![Prédio Ibmec Barra](images/Imagem2_Ibmec_Predio.png) |

| 3. Visão Geral do Cenário |
| :---: |
| ![Cenário Geral](images/Imagem4_CenarioGeral.png) |

---

## 📄 Relatório Técnico e Animação (AP2)

### 1. Objetos Autorais e Elementos
1. **`OBJ_Predio_IbmecBarra`**: Representa a infraestrutura do campus Ibmec Barra ao fundo.
2. **`OBJ_Ponte_Conexao`**: Ponte estaiada simbolizando a conexão com o mercado global.
3. **Cenário Auxiliar**: Pedestal da palavra, canteiros com árvores *low-poly* e postes de iluminação.

### 2. Organização do Outliner
- 📁 `AP1_Ibmec_Conceito`
  - 📁 `01_Palavra_Ibmec`
  - 📁 `02_Objetos_Autorais`
  - 📁 `03_Cenario_Auxiliar`
  - 📁 `04_Cameras_Luzes`

### 3. Plano de Animação (AP2)
- **Frames 1–100:** Câmera faz aproximação (*Dolly In*) revelando o campus e o piso da maquete.
- **Frames 101–260:** Rotação orbital suave destacando a ponte estaiada e o prédio Ibmec Barra.
- **Frames 261–360:** Câmera desacelera e fixa a palavra Ibmec centralizada e iluminada.
EOF
