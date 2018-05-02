# Migracion-PDI
#PARTE RAFAEL
from PIL import Image #nos servirá para abrir o manipular una imagen en python
import os
import numpy as np
import matplotlib.pyplot as plt
from skimage import io

clear = lambda: os.system('cls') #on Windows System
clear()

I = Image.open("C:/Users/qwerty/Desktop/PDI_spyder/imagenes/1.png")
I.show()
I1=I.convert('L') # convierte a escala de grises
I1.show()


a=np.asarray(I1,dtype=np.float32)
Image.fromarray(a.astype(np.uint8)).save("prueba.jpg")  # primero convierte "a" a uint8, y luego a un objeto "imagen"

image=io.imread("prueba.jpg")/255.0 # imread lee las imagenes con los pixeles codificados como enteros 
# en el rango 0-255. Por eso la convertimos a flotante y en el rango 0-1
print("- Dimensiones de la imagen:")
print(image.shape)
plt.imshow(image,vmin=0,vmax=1)


csal=[237,28,36]
cnosal=[0,0,255]

        

indsal=(I1[:,:,1]==csal(1) and I1[:,:,2]==csal(2)and I1[:,:,3]==csal(3));
            
#######################
CODIGO DE HECTOR, LO MISMO QUE HIZO RAFA PERO MAS COMPACTO :3
def prueba1():
    
    ruta = ('C:/CursoPython/imagenes/1.png')
    ruta2 = ('C:/CursoPython/imagenes/2.png')
    imo = Image.open(ruta)
    imo = imo.convert('L')
    print(imo.size)
    print(imo.mode)
    

    im = io.imread(ruta2)
    print(im.shape)
    imout = np.zeros(im.size)  
    [filas, columnas] = im.size
    
    csal = [237,28,36]
    cnosal = [0,0,255]
