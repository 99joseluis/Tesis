# Notas de las funciones utilizadas en el notebook ImagesProcessing 

##  1.- Función: cv2.treshold(src, threshValue, maxVal, TresholdTechnique)

- src : Imagen a umbralizar (Necesita estar a escala de grises)

- threshValue: Valor del umbral a utulizar

- maxVal: Valor maximo de los pixeles a utilizar

- ThresholdTechnique: Tecnica a utilizar de treshold, entre las mas cupadas se encuentran:
	- cv2.THRESH_BINARY: utiliza el valor del umbral como punto medio, es decir, todos los pixeles que sobrepasen este valor se le será asignado el maximo valor (maxVal), de lo contrario se les asigna el valor 0 
	
	$$
	\begin{equation}    
		dst(x,y) = \left[        
		\begin{array}{ll}           
	    	maxVal  &   \mathrm{si\ } src(x,y) > thresh\\            			0   & \mathrm{en\ otro\ caso}        
	    \end{array}    
	    \right.
	\end{equation}
	$$
	
	- cv2.THRESH_BINARY_INV: Es lo contrario al THRESH_BINARY
	  $$
	  \begin{equation}    
	  	dst(x,y) = \left[        
	  	\begin{array}{ll}           
	      	0  &   \mathrm{si\ } src(x,y) > thresh\\            			maxVal   & \mathrm{en\ otro\ caso}        
	      \end{array}    
	      \right.
	  \end{equation}
	  $$
	  
	- cv2.THRESH_TRUNC: utiliza el valor de umbral como punto maximo, es decir, todos los pixeles que sobrepasen este valor se les asignará el valor del umbral y los que sean menores que el umbral permaneceran del mismo valor
	  $$
	  \begin{equation}    
	  	dst(x,y) = \left[        
	  	\begin{array}{ll}           
	      		thresh  &   \mathrm{si\ } src(x,y) > thresh\\   			src(x,y)   & \mathrm{en\ otro\ caso}        
	      \end{array}    
	      \right.
	  \end{equation}
	  $$
	  
	  $$
	  
	  $$
	
	- cv2.THRESH_TOZERO: Todos los pixeles que se encuentren por debajo o igual que el valor de umbral se les asignará el valor 0, mientras que los que lo sobrepasen permaneceran igual
	  $$
	  \begin{equation}    
	  	dst(x,y) = \left[        
	  	\begin{array}{ll}           
	      	src(x,y)  &   \mathrm{si\ } src(x,y) > thresh\\   			0   	  &   \mathrm{en\ otro\ caso}        
	      \end{array}    
	      \right.
	  \end{equation}
	  $$
	  
	- cv2.THRESH_TOZERO_INV: 


$$
\begin{equation}    
	dst(x,y) = \left[        
	\begin{array}{ll}           
    	0  			  &   \mathrm{si\ } src(x,y) > thresh\\ 
        src(x,y)	  &   \mathrm{en\ otro\ caso}        
    \end{array}    
    \right.
\end{equation}
$$

## 2.- Función: cv2.calcHist(src, channels, mask, histSize, ranges[hist[accumulate]])

- src: Imagen fuente
- channels: lista de canales a usar para calcular el histograma
- mask: mascara opcional del mismo tamaño de la imagen en un arreglo de 8 bits (escala de grises)
- histSize: Tamaño de los histogramas en cada dimensión
- ranges:  arreglo de arreglos del histograma que contiene cada dimensión
  - hist: Histograma de salida
  - accumulate: Bandera de acumulación, permite calcular un solo histograma a partir de varios arreglos.

 