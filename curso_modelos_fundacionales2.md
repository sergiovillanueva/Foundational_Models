# Curso: Modelos Fundacionales y Detección de Objetos en Visión Artificial

## Objetivos

Ofrecer una comprensión sólida de los **modelos fundacionales aplicados a la visión artificial**, combinando teoría y práctica intensiva.  
Los estudiantes aprenderán a utilizar modelos de última generación disponibles en **Hugging Face Transformers** para tareas como detección de objetos, segmentación, clasificación multimodal, estimación de pose, superresolución y OCR.  

También se abordarán temas relacionados con **licencias, gestión de entornos (Colab y local)** y buenas prácticas en el uso de modelos preentrenados.

---

## 📅 Viernes (4 horas)

### 1. Detección de Objetos (1h 30 min)

Se introduce la detección de objetos como punto de partida, mostrando cómo las arquitecturas modernas sientan las bases de los modelos fundacionales de visión, extendiendo estos conceptos hacia tareas más generales y multimodales.

- Introducción a la detección de objetos.  
- Comparación entre arquitecturas clásicas y modernas.  
- **YOLO:** concepto, versiones y ventajas.  
- **RF-DETR:** arquitectura basada en Transformers.  
- Repaso del entorno / uso en Colab.  
- 📓 *Notebook práctico:* detección en imágenes industriales con modelos preentrenados (YOLO y RF-DETR).  
- Limitaciones y evolución hacia arquitecturas fundacionales.

---

### 2. Uso práctico de Hugging Face y gestión de entornos (30 min)

Este bloque explica cómo buscar, descargar y ejecutar modelos en **Hugging Face**, gestionando versiones y dependencias tanto en Google Colab como en local.

- Qué es Hugging Face (Model Hub, Datasets, Spaces).  
- Cómo usar `from_pretrained`.  
- Concepto de *token* y caché local.  
- Licencias comunes en IA (Apache 2.0, MIT, GPL...).  
- 📓 *Notebook práctico:* descargar un modelo, inspeccionar sus archivos y probar inferencia básica.

🕒 Descanso (15 min)

---

### 3. Modelos Fundacionales Multimodales (1h 45 min)

Explicación de la evolución conceptual desde los modelos unimodales (texto o imagen) hacia los **modelos multimodales**, culminando en los **Vision-Language Models (VLMs)** capaces de razonar sobre texto e imagen.

- Qué son los modelos fundacionales y su importancia.  
- De NLP a visión: CLIP, SAM, DINO.  
- **CLIP:** relación texto-imagen.  
- **BLIP:** captioning y preguntas visuales.  
- **Grounding DINO:** detección guiada por texto.  
- **Qwen2.5-VL (VLM):** razonamiento visual y textual avanzado.  
- Comparación entre CLIP / BLIP y un VLM moderno.  
- 📓 *Notebook práctico:* clasificación, captioning y detección con prompts (CLIP, BLIP, Grounding DINO, Qwen2.5-VL).

---

## 📅 Sábado (4 horas)

*(El bloque de DINO/DINOv3 se presenta antes de la segmentación, por su relación conceptual como base de SAM.)*

### 1. Repaso del viernes (30 min)

- Detección con YOLO y RF-DETR.  
- CLIP, BLIP, Grounding DINO y Qwen2.5-VL.  
- Preguntas rápidas y repaso práctico.

---detección → multimodalidad → auto-supervisión → segmentación → pose → extras

### 2. DINO / DINOv3 (1h)

- DINO/DINOv3 como extractores de características visuales.  
- Aprendizaje auto-supervisado y similitud de parches.  
- Relación con **Depth Anything V2** y embeddings multimodales.  
- Visualización de features y proyecciones t-SNE.  
- 📓 *Notebook práctico:* embeddings + t-SNE / similitud de regiones.

---

### 3. Segmentación con SAM y variantes (1h)

- **Segment Anything (SAM2):** segmentación universal y promptable.  
- Segmentación guiada con **Grounding DINO** y **VLMs**.  
- Casos industriales: segmentar componentes o zonas específicas.  
- 📓 *Notebook práctico:* segmentación interactiva y segmentación por texto.

🕒 Descanso (15 min)

---

### 4. Estimación de Pose (45 min)

- Qué es y para qué sirve.  
- Modelos sencillos para keypoints humanos en Hugging Face.  
- 📓 *Notebook práctico:* detección de pose humana sobre fotos o video.

---

### 5. Otras tareas de visión fundacional (1h)

- **OCR:** reconocimiento de texto con EasyOCR (ligero y fácil de usar).  
- **Superresolución:** mejora de calidad visual con Swin2SR.  
- **Background Removal:** eliminación de fondo con RMBG.  
- **Matching:** correspondencia de puntos con LightGlue + SuperPoint.  
- 📓 *Notebook práctico:* pruebas rápidas con cada técnica.

---

## 🧩 Modelos utilizados

| Categoría                          | Tarea principal             | Modelo / Método         | ID en Hugging Face                          |
| ---------------------------------- | --------------------------- | ----------------------- | ------------------------------------------- |
| Detección de objetos               | Detección clásica           | YOLOv8                 | `ultralytics/YOLOv8`                        |
| Detección de objetos (Transformer) | Detección moderna           | RF-DETR                | `roboflow/rf_detr`                          |
| Multimodal                         | Clasificación / Captioning  | CLIP                   | `openai/clip-vit-large-patch14`             |
| Multimodal                         | Captioning / VQA            | BLIP                   | `Salesforce/blip-image-captioning-base`     |
| Detección guiada por texto         | Detección / Segmentación    | Grounding DINO         | `IDEA-Research/grounding-dino-base`         |
| Vision-Language Model (VLM)        | Razonamiento multimodal     | Qwen2.5-VL             | `Qwen/Qwen2.5-VL-3B-Instruct`               |
| Auto-supervisado                   | Extracción de features      | DINOv3                 | `facebook/dinov3-vitb16-pretrain-lvd1689m`  |
| Segmentación                       | Segmentación universal      | SAM2                   | `facebook/sam2-hiera-base-plus`             |
| Profundidad                        | Estimación de profundidad   | Depth Anything V2      | `depth-anything/Depth-Anything-V2-Small-hf` |
| Pose humana                        | Keypoints humanos           | MoveNet                | `google/movenet-singlepose-lightning`       |
| OCR                                | Reconocimiento de texto     | EasyOCR                | `JaidedAI/EasyOCR`                          |
| Matching                           | Correspondencia de puntos   | LightGlue + SuperPoint | `ETH-CVG/lightglue_superpoint`              |
| Superresolución                    | Mejora de calidad visual    | Swin2SR                | `caidas/swin2SR-classical-sr-x4-64`         |
| Eliminación de fondo               | Segmentación de fondo       | RMBG-1.4               | `briaai/RMBG-1.4`                           |
