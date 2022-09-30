# 1. Para la descarga e instalación de Python analiza el siguiente vídeo y visita el sitio oficial.

https://www.youtube.com/watch?v=nXgxe3JM7Rc

https://www.python.org/downloads/

# 2. Para la descarga e instalación de labelImg analiza la serie de pasos descrita en la fuente de esta sección.
 
 
 Requisitos: Python instalado.
 
 Los siguientes pasos se realizan desde la GUI.
 1. Seleccionar la ruta absoluta donde se almacenara labelImg.
 2. Descarga del directorio de labelImg. Descarga desde aquí: github.com/tzutalin/labelImg
 3. Descomprime el directorio labelImg-master (puedes renombrar este directorio).
 4. Instalar dependencias: pip install PyQt5, pip install lxml.
 5. Desde la CLI acceda a la ruta absoluta del directorio de labelImg y compile con el siguiente comando: pyrcc5 -o libs/resources.py resources.qrc
 6. Abrir aplicación labelImg: 


 cd C:\Users\ohc\Documents\Clase CuSur\Taller\labelImg
 
 
 python labelImg.py
 
 
 Etiquetar el dataset y guardar usando la siguiente estructura:

--train_data

  -- images  
  
      --train      
      
      --val      
      
  -- labels  
  
      --train     
      
      --val


 Fuente:
 https://1step2learn.com/wp/en/machine-learning/install-labelimg-on-windows/


# 3. Entrenamiento de la red neuronal.


Seguiremos la guía del sitio oficial YoloV5: https://github.com/ultralytics/yolov5


# 4. Sobre el codigo del enlace anterior haremos las siguientes modificaciones

  !unzip -q ../train_data.zip -d ../




Creamos un archivo customdata.yaml con la siguiente información, y guardar en la ruta yolov5/data

path: ../train_data  # dataset root dir

train: ../train_data/images/train/  # train images 

val: ../train_data/images/val/  # val images 

test:  # test images (optional)

Classes
nc: 1  # number of classes

names: ['gun']  # class names



Finalmente ejecutamos la linea de entrenamiento

!python train.py --img 640 --batch 4 --epochs 100 --data customdata.yaml --weights yolov5s.pt --cache


# 5. Creamos un archivo customdata.yaml con la siguiente información, y guardar en la ruta yolov5/data
