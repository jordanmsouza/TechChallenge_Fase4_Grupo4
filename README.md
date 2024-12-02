# **Documentação do Projeto de Análise de Vídeo**

---

## **1. Introdução**
Este projeto é parte do Tech Challenge e foi desenvolvido para realizar análise de vídeo utilizando reconhecimento facial, análise de expressões emocionais, detecção de atividades e geração de relatórios. A aplicação processa vídeos, identifica emoções e atividades, e produz um resumo detalhado da análise.

---

## **2. Funcionalidades**
1. **Reconhecimento Facial:**
   - Detecção de rostos no vídeo utilizando Haar Cascade.
   - Desenho de caixas delimitadoras verdes ao redor dos rostos detectados.

2. **Análise de Expressões Emocionais:**
   - Utiliza a biblioteca DeepFace para identificar emoções (ex.: felicidade, tristeza, etc.).
   - Aplica um mecanismo de suavização para reduzir mudanças bruscas entre emoções detectadas.

3. **Detecção de Atividades:**
   - Identificação de ações humanas como levantar a mão, acenar, apertar as mãos ou dançar.
   - Baseado na detecção de poses corporais com MediaPipe.

4. **Geração de Relatório:**
   - Total de frames processados.
   - Contagem de ocorrências de emoções detectadas.
   - Contagem de atividades identificadas.

---

## **3. Tecnologias e Bibliotecas Utilizadas**
- **Python**: Linguagem principal.
- **OpenCV**: Processamento de vídeo e detecção de rostos.
- **DeepFace**: Análise de emoções faciais.
- **Detectron2**: Detecção de objetos para identificar corpos humanos.
- **MediaPipe**: Detecção de poses corporais.
- **TQDM**: Exibição de barra de progresso.
- **NumPy**: Manipulação de dados matriciais.

---

## **4. Estrutura do Código**
### **Instalação de Dependências**
As bibliotecas requeridas são instaladas utilizando pip. Certifique-se de configurar o ambiente antes da execução:
```bash
!pip install opencv-python numpy deepface mediapipe tqdm
!pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
!pip install 'git+https://github.com/facebookresearch/detectron2.git'


