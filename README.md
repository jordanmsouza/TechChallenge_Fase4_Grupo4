# **Documentação do Projeto de Análise de Vídeo**

---

## **1. Introdução**
Este projeto é parte do Tech Challenge e foi desenvolvido para realizar análise de vídeo utilizando reconhecimento facial, análise de expressões emocionais, detecção de atividades e geração de relatórios. A aplicação processa vídeos, identifica emoções e atividades, e produz um resumo detalhado da análise.

---

## **2. Funcionalidades**
1. **Reconhecimento Facial:**
   - Detecção de rostos no vídeo utilizando Haar Cascade.
   - Marcações delimitadoras verdes ao redor dos rostos detectados.
   - Marcações delimitadoras azuis ao redor dos corpos para detecção de atividades.

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
!pip install opencv-python
!pip install numpy
!pip install deepface
!pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
!pip install 'git+https://github.com/facebookresearch/detectron2.git'
!pip install mediapipe
!pip install tqdm
```
---

## **5. Funções Principais**
1. `setup_detectron2()`
   - Configura o modelo Detectron2 para detecção de pessoas.

2. `analyze_face_emotions(frame, boxes, last_emotion)`
   - Detecta e suaviza mudanças de emoções em rostos identificados.

3. `detect_activities(frame, pose_results)`
   - Identifica atividades humanas baseadas em poses corporais.

4. `analyze_video(video_path)`
   - Processa o vídeo, executa as análises (rostos, emoções, atividades) e gera um relatório.
  
---

## **6. Como Executar** 
1. Clone o repositório e configure o ambiente Python com as dependências listadas.
2. Certifique-se de ter o vídeo para análise disponível no caminho especificado.
3. Execute o script principal:
```python
video_path = "/caminho/para/seu/video.mp4"
analyze_video(video_path)
```
4. Os resultados serão salvos na pasta de saída definida no script (output_dir).

---

## **7. Resultados Gerados** 
1. Vídeo Processado:
   - Arquivo de saída contém marcações visuais para rostos e corpos, sendo as emoções representadas por retangulos verdes e atividades com retângulos azuis.
   - Salvo no diretório configurado `(output_dir)`.

2. Resumo da Análise:
    - Texto com:
         - Emoções detectadas e suas ocorrências.
         - Atividades identificadas e suas ocorrências.
    - Salvo como `video_analysis_summary_1.txt` no mesmo diretório.

---

## **8. Observações**
1. Desempenho:
   - As detecções de de atividades não são totalmente acertivas, necessitando de ajustes finos para de detecções de atividades mais complexas.
2. Ambiente:
   - O uso do colab gratuíto pode onerar o processamento da análise de video, já que o uso da GPU T4 expira a um dado tempo de processamento. Recomenda-se o uso de GPU para maior eficiência ou a versão paga do colab.

---
## **9. Links úteis**
1. Base para execução do projeto e arquivos de saída disponível em: `https://drive.google.com/drive/folders/1Y8kUwzdkyosy-1BFiBXPOmSc8Fd-EtWn?usp=sharing`
2. Video explicativo youtube: `https://youtu.be/JKgpiRG7rJE?si=72Wx7OrgSzmJ3efv`
