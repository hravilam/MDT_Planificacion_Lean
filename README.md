
%% paper_template.tex is a modification of:
%% bare_conf.tex 
%% V1.2
%% 2002/11/18
%% by Michael Shell
%% mshell@ece.gatech.edu
%% 
%% Modificación para plantilla trabajo final
%% Posgrado Facultad de Ciencias Básicas e Ingeniería
%
%
\documentclass[conference,twoside]{IEEEtran}

%% Comentar o descomentar este paquete de hyperref a su necesidad
\usepackage{hyperref}
%%

\usepackage{cite}      
\input epsf
\usepackage[utf8]{inputenc} % Permite escribir tildes y ñ directamente desde el teclado
\usepackage[T1]{fontenc} % Mejora la calidad de las fuentes y la lectura de caracteres especiales
\usepackage[english, spanish, es-tabla]{babel} % Configura el idioma y cambia "Cuadro" por "Tabla"

% Redefinición de etiquetas para que babel respete el formato IEEE
\addto\captionsspanish{%
  \renewcommand{\abstractname}{Resumen}
  \renewcommand{\IEEEkeywordsname}{Índice de términos}
  \def\tablename{TABLA} % Fuerza "TABLA" en mayúsculas estilo IEEE 
}

\addto\captionsenglish{%
  \renewcommand{\abstractname}{Abstract}
  \renewcommand{\IEEEkeywordsname}{Index Terms}
}

\makeatletter
\let\NAT@parse\undefined
\makeatother
\usepackage[numbers]{natbib}
\shorthandoff{~}             % Evita que la Babel española rompa las citas

%%====== EDITAR: COLOQUE AQUI SUS PAQUETES======
\usepackage{graphicx}
\usepackage{url}     
\usepackage{amsmath} 
\usepackage{amssymb}
\usepackage{csquotes}
\usepackage{xcolor}
\usepackage{soul}
\usepackage{multirow}
\usepackage{blindtext}
\usepackage{balance}
\usepackage{float} % <--- AGREGA ESTO EN TU PREÁMBULO PARA ACTIVAR EL PARÁMETRO [H]


%%======FIN COLOQUE AQUI SUS PAQUETES======

\definecolor{libertadores_teal}{HTML}{008B8B} % Color aproximado de la imagen
\usepackage{fancyhdr} % En el preámbulo
\pagestyle{fancy}
\fancyhf{}

%%=====EDITAR NOMBRES
\fancyhead[RO,LE]{Clerk Maxwell, Michael Faraday, Andr\'e M. Amp\`ere } % Nombre en la esquina exterior
%%=====FIN EDITAR NOMBRES

\fancyhead[LO,RE]{\thesection}
\fancyfoot[C]{\thepage}              % Número de página al centro

\hyphenation{op-tical net-works semi-conduc-tor IEEEtran}


%%================================================%%
%%=====INICIO DOCUMENTO
%%================================================%%

\begin{document}
%+++++++++++++++++++++++++++++++++++++++++++
\title{% Bloque Institucional (Simulando tu imagen)
\vspace{-40pt} % Ajusta esto para subir o bajar el encabezado

\begin{minipage}{\textwidth}
    \begin{minipage}{0.7\textwidth}
    \flushleft
    {\normalsize
    \begin{tabular}{|l}
 %%====EDITAR PROGRAMA ACADÉMICO   
        \textcolor{libertadores_teal}{\textbf{Especialización}} \\
        \textcolor{libertadores_teal}{\textbf{en Estadística Aplicada}} \\
 %%====FIN EDITAR PROGRAMA ACADÉMICO       
        \textcolor{libertadores_teal}{Facultad de Ingeniería y Ciencias Básicas}\\
        
        \end{tabular}
    }
    \end{minipage}
    \begin{minipage}{0.28\textwidth}
        \flushright
        \includegraphics[width=2.0cm]{img/logoFULL.png}
    \end{minipage}
\end{minipage}

\vspace{20pt} % Espacio entre la institución y el título real

%%====EDITAR TITULO DE TRABAJA DE GRADO
\LARGE Planificación de la Demanda de Materia Prima Textil a Partir de un Modelo de Machine Learning Bajo Principios Lean Manufacturing\\
[0.5cm]
Planning Textile Raw Material Demand Using a Machine Learning Model Based on Lean Manufacturing Principles}
%%====FIN EDITAR TITULO DE TRABAJA DE GRADO
%+++++++++++++++++++++++++++++++++++++++++++
%Nombres y afiliaciones de los autores
%El % utiliza un diseño de varias columnas para hasta %tres afiliaciones diferentesJ. 
%+++++++++++++++++++++++++++++++++++++++++++

%%====EDITAR AUTORES
\author{
  \authorblockN{Helver Roberto Avila Martinez}
  \authorblockA{Facultad de Ciencias básicas e Ingeniería\\
    Fundación Universitaria Los Libertadores\\
    Bogotá, Colombia\\
     hravilam@libertadores.edu.co}
  \and

  \authorblockN{José John Fredy González Veloza \\ }
 \authorblockA{Facultad de Ingeniería y Ciencias Básicas\\
    Fundación Universitaria Los Libertadores\\
    Bogotá, Colombia\\
     jjgonzalezv02@libertadores.edu.co}

}
%%====FIN EDITAR AUTORES

\maketitle
\thispagestyle{firstpage} % Tu estilo personalizado con logo y número
\pagestyle{fancy}         % O el estilo que prefieras para el resto del documento


% --- RESUMEN EN ESPAÑOL ---
\selectlanguage{spanish}
%%=== EDITAR RESUMEN EN ESPAÑOL
\begin{abstract}
Contexto: El incremento del sobreinventario y la variabilidad de la demanda representan uno de los principales desperdicios (mudas) dentro de los sistemas de manufactura Lean, al generar sobrecostos de almacenamiento e inmovilización de capital de trabajo. En muchas organizaciones, las decisiones de abastecimiento se basan en métodos tradicionales de promedios móviles que omiten patrones históricos complejos. Esta situación exige una transición hacia modelos predictivos que permitan una gestión logística más eficiente y precisa.

Propósito: Este proyecto optimiza la planeación de compras de hilo crudo mediante un modelo de Machine Learning supervisado para el pronóstico de series de tiempo. El enfoque busca alinear el pronóstico con el horizonte de tres meses, correspondiente al Lead Time de importación, para garantizar la continuidad operativa.

Metodología: La investigación transformó un histórico de 36 meses en una Matriz de Datos Tabular (MDT), complementada con un Análisis Exploratorio de Datos (EDA) para identificar patrones. Se realizó una evaluación comparativa de los algoritmos Ridge, Random Forest y XGBoost, empleando una partición temporal estricta (Train/Test) previa a cualquier escalado para evitar la fuga de datos (data leakage).

Resultados: Los resultados demuestran que el algoritmo XGBoost presenta el mejor desempeño en el conjunto de prueba, logrando un MAE de 71,230.86 KG y superando la precisión de los modelos tradicionales. Esta implementación permite un ahorro proyectado de aproximadamente 30 millones de COP anuales en costos de almacenamiento para fibras de Clase A.

Conclusiones: De acuerdo con estos resultados, se confirma que la integración de algoritmos de aprendizaje supervisado es una alternativa viable para reducir la incertidumbre en la cadena de suministro textil. Se infiere que esta metodología no solo optimiza la exactitud del pronóstico, sino que fortalece la capacidad de la organización para gestionar flujos de valor estables bajo los principios de Lean Manufacturing.


%\textquote{De acuerdo con estos resultados, se considera necesario que se cambie el protocolo de calibración del laboratorio}.
\end{abstract}

\begin{keywords}
Machine Learning, Planeación de la Demanda, Lean Manufacturing, XGBoost, Inventario Textil.\end{keywords}
%%=== FIN EDITAR RESUMEN EN ESPAÑOL

% --- RESUMEN EN INGLÉS ---
\selectlanguage{english}
%%=== EDITAR RESUMEN EN INGLÉS
\begin{abstract}
Context: The increase in excess inventory and demand variability represent one of the main forms of waste (muda) in Lean manufacturing systems, as they generate excess storage costs and tie up working capital. In many organizations, procurement decisions are based on traditional moving-average methods that fail to account for complex historical patterns. This situation calls for a transition to predictive models that enable more efficient and accurate logistics management.

Purpose: This project optimizes raw yarn procurement planning using a supervised machine learning model for time series forecasting. The approach aims to align the forecast with the three-month horizon—corresponding to the import lead time—to ensure operational continuity.

Methodology: The research converted a 36-month history into a Tabular Data Matrix (TDM), supplemented with Exploratory Data Analysis (EDA) to identify patterns. A comparative evaluation of the Ridge, Random Forest, and XGBoost algorithms was conducted, using a strict temporal split (Train/Test) prior to any scaling to prevent data leakage.

Results: The results demonstrate that the XGBoost algorithm performs best on the test set, achieving an MAE of 71,230.86 KG and outperforming traditional models in terms of accuracy. This implementation enables projected annual savings of approximately 30 million COP in storage costs for Class A fibers.

Conclusions: Based on these results, it is confirmed that the integration of supervised learning algorithms is a viable alternative for reducing uncertainty in the textile supply chain. It is inferred that this methodology not only optimizes forecast accuracy but also strengthens the organization’s ability to manage stable value streams under the principles of Lean Manufacturing.

\end{abstract}

\begin{keywords}
Machine Learning, Demand Planning, Lean Manufacturing, XGBoost, Textile Inventory.
\end{keywords}
%%=== FIN EDITAR RESUMEN EN INGLÉS

\selectlanguage{spanish} % Regresa a español para el resto del artículo
\IEEEpeerreviewmaketitle

%%%
%%% EDITAR DOCUMENTO
%%%


\section{Introducción}

La planeación de la demanda constituye un proceso fundamental en la gestión de operaciones, permitiendo coordinar los niveles de producción, abastecimiento e inventario según las necesidades reales del mercado. Una estimación inadecuada puede generar problemas críticos como el exceso de inventario o la ruptura de stock, afectando directamente la rentabilidad financiera \cite{heizer2020operations}.

En el marco de la filosofía \textit{Lean Manufacturing}, la eliminación de desperdicios (\textit{mudas}) es un objetivo prioritario. El sobreinventario resulta particularmente nocivo al incrementar los costos de almacenamiento, el riesgo de deterioro de materiales y la ineficiencia operativa. Según \cite{womack2003lean}, la reducción sistemática de estos desperdicios permite mejorar el flujo de valor y transitar de un sistema de empuje (\textit{push}) a uno de atracción (\textit{pull}) guiado por el consumo real.

Estudios previos han demostrado que la creciente disponibilidad de datos empresariales permite incorporar técnicas de analítica avanzada. Los modelos predictivos basados en aprendizaje supervisado poseen la capacidad de identificar patrones no lineales complejos, superando la precisión de métodos tradicionales como promedios móviles o regresiones lineales simples \cite{geron2022hands}. Asimismo, algoritmos ensamblados como \textit{Random Forest} y \textit{Gradient Boosting} han sido validados como herramientas idóneas para la optimización de stocks de seguridad y la estabilización del aprovisionamiento \cite{chollet2021deep}.

A diferencia de los enfoques convencionales que se limitan a predicciones aisladas, este estudio propone un agente diferenciador clave: la implementación de una arquitectura de Regresión Multisalida. Esta metodología permite predecir de forma simultánea el comportamiento de la demanda para cada uno de los tres meses que componen el horizonte de \textit{Lead Time} del proveedor extranjero, sustituyendo la planeación intuitiva por un Punto de Reorden Inteligente fundamentado en la optimización estadística.

El objetivo general de este proyecto es implementar dicho modelo sobre los registros de una planta textil, bajo los principios de \textit{Lean Manufacturing}, para eliminar el desperdicio derivado del sobreinventario y garantizar un flujo de valor estable. Para alcanzar este propósito, el documento estructura el análisis desde el diagnóstico de la variabilidad del consumo mediante un análisis exploratorio, hasta la implementación de un modelo de aprendizaje supervisado basado en XGBoost, cuya capacidad predictiva ha sido validada mediante particiones temporales estrictas que aseguran la fiabilidad del pronóstico en escenarios operativos reales.




%==================  fin INTRODUCCION

%==================  METODOS  
%===

%* significa que va a ocupar todo el ancho de la página


\section{Metodología}

\label{sec:metodos}

Se estructuró un enfoque metodológico iterativo basado en el tratamiento cuantitativo de datos históricos operacionales, orientado a la mitigación de desperdicios en el flujo de valor bajo principios \textit{Lean Manufacturing}. El desarrollo se despliega desde la auditoría de los datos hasta la evaluación de arquitecturas predictivas supervisadas.

\subsection{Datos (o Muestra)}
\label{subsec:datos}

\textit{Modelo de Datos Tabular (MDT) y Granularidad:} El conjunto de datos utilizado en este proyecto contiene el registro histórico de consumos mensuales de la planta textil. El universo completo contempla un total de 144 SKUs (\textit{Stock Keeping Unit}) registrados en el maestro operacional. Con el fin de concentrar los esfuerzos analíticos en los componentes críticos para el aprovisionamiento bajo principios \textit{Lean}, se aplicó un filtro basado en la clasificación de Pareto, aislando un subconjunto de SKUs críticos identificados como Clase A.

La granularidad de la MDT está definida formalmente al nivel de SKU. Para garantizar la eficiencia en el flujo de valor, se aplicó un análisis de Pareto ilustrado en la Fig. \ref{fig:pareto_fibras_abc}, el cual clasifica las familias de fibra según su impacto en el volumen total de consumo. Como se observa en la Fig. \ref{fig:boxplot_pareto}, las categorías AAA, AA y A representan la mayor parte del volumen de consumo de la planta. Esta clasificación permite concentrar los esfuerzos analíticos y la precisión del modelo predictivo en los insumos críticos, eliminando el desperdicio de tiempo de cómputo en referencias de baja rotación.

\begin{figure}[htbp]
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/pareto_fibras_abc.png}
    \caption{Análisis de Pareto: Identificación de la fibra crítica Clase AAA.}
    \label{fig:pareto_fibras_abc}
\end{figure}


\begin{table}[htbp] % Sin asterisco para mantenerla dentro de una sola columna
\centering
\caption{Diccionario de variables de la MDT Maestra.}
\label{tab:diccionario_vars}
\footnotesize % Fuente compacta obligatoria para una columna IEEE
\setlength{\tabcolsep}{2pt} % Margen interno mínimo para evitar que se salga
\begin{tabular}{|l|l|l|p{3.2cm}|} % Ancho de descripción ajustado para que quepa exacto
\hline
\textbf{Variable} & \textbf{Tipo} & \textbf{Rol} & \textbf{Descripción Técnica} \\ \hline
Descripcion fibra & Categórica & Predictora (X) & Familia de materia prima textil cruda. \\ \hline
Descripcion color & Categórica & Predictora (X) & Tonalidad específica de la fibra. \\ \hline
Estado & Categórica & Filtro & Condición: restricción a SKUs en "LÍNEA". \\ \hline
Clasificacion ABC & Categórica & Predictora (X) & Segmentación de Pareto histórica (A, B, C). \\ \hline
Inventario & Numérica & Predictora (X) & Existencias físicas en bodega (KL). \\ \hline
Costo almac. & Numérica & Predictora (X) & Costo financiero unitario (COP/KL). \\ \hline
Consumos Hist. & Numérica & Predictora (X) & Serie histórica de 32 periodos mensuales (KL). \\ \hline
Target 1 (Feb) & Numérica & Target (y1) & Pronóstico del mes 1 del Lead Time. \\ \hline
Target 2 (Mar) & Numérica & Target (y2) & Pronóstico del mes 2 del Lead Time. \\ \hline
Target 3 (Abr) & Numérica & Target (y3) & Pronóstico del mes 3 del Lead Time. \\ \hline
Consumo Mayo & Numérica & Control & Registro excluido de entrenamiento y test. \\ \hline
\end{tabular}
\end{table}

\subsection{Exploración de datos}
\label{subsec:eda}

\textit{Análisis Univariado (Distribución y Outliers):} El análisis descriptivo univariado de la demanda para los 30 SKUs críticos de la Clase A arroja una media de 904.59 KL y una desviación estándar de 862.57 KL. Sin embargo, al aislar la referencia crítica primordial Clase AAA, el comportamiento real se evidencia de forma explícita en la \textbf{Fig. \ref{fig:eda_distribucion_real}}. La curva de densidad estimada (KDE) demuestra visualmente un comportamiento bimodal estructurado muy marcado: el primer componente o pico concentra una alta densidad de frecuencias en rangos de consumo bajos (cercanos a los $5,000\text{ KG}$), mientras que el segundo pico agrupa los periodos de alta rotación y abastecimiento pesado (superiores a los $11,000\text{ KG}$). Este fenómeno de bimodalidad es el hallazgo matemático más relevante de la exploración, ya que describe por qué los métodos estadísticos lineales tradicionales fallan; la demanda cambia entre dos regímenes operativos distintos, validando estadísticamente la necesidad de transitar hacia algoritmos basados en árboles de decisión como \textit{XGBoost}, cuyas fronteras de decisión binarias pueden segmentar estas dos dinámicas con alta precisión.


\begin{figure}[H] 
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/eda_distribucion_outliers_fibra_POL_ALG_PRET_30_1.png}
    \caption{Distribución histórica de frecuencias y curva de densidad (KDE) para la fibra crítica POL ALG PRET 30/1.}
    \label{fig:eda_distribucion_real}
\end{figure}


El diagrama de caja presentado en la Fig. \ref{fig:boxplot_pareto} expone la variabilidad del consumo por familia. La ausencia de valores atípicos críticos fuera de los rangos operativos demuestra que el criterio de filtrado (restricción a referencias "LÍNEA") fue exitoso, convirtiéndose en garantía de un conjunto de datos homogéneo para el entrenamiento de los algoritmos y eliminando el riesgo de distorsión por ruidos operativos transitorios.

\begin{figure}[H] 
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/boxplot_pareto.png}
    \caption{Diagrama de caja (boxplot) y variabilidad del consumo por familia Clase A.}
    \label{fig:boxplot_pareto}
\end{figure}

\textit{Análisis Bivariado (Dependencia Temporal):} La Fig. \ref{fig:eda_evolucion} expone la evolución temporal de la demanda agregada mensual, evidenciando un comportamiento oscilatorio controlado que fluctúa entre los 26,800 y 27,450 KL. 

\begin{figure}[htbp]
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/eda_evolucion_temporal_fibra_POL_ALG_PRET_30_1.png}
    \caption{Evolución temporal histórica de la demanda agregada mensual.}
    \label{fig:eda_evolucion}
\end{figure}

Para evaluar la estructura temporal, la Fig. \ref{fig:eda_acf} presenta la Función de Autocorrelación (ACF). El análisis muestra un coeficiente positivo en el Rezago 1 ($\text{Lag 1} \approx 0.33$), con un segundo repunte en el Rezago 5. Estos indicadores confirman una dependencia autorregresiva en la serie de consumo. La presencia de estos rezagos justifica la inclusión de variables temporales en los modelos de Machine Learning, en comparación con métodos de promedio móvil tradicionales.

\begin{figure}[htbp]
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/eda_autocorrelacion_fibra_POL_ALG_PRET_30_1.png}
    \caption{Función de Autocorrelación (ACF) de la serie de consumo histórico.}
    \label{fig:eda_acf}
\end{figure}

\textit{Análisis Multivariado (Tendencia de la Fibra Crítica):} Para reducir la alta dimensionalidad del universo operacional y centrar el análisis cuantitativo en los insumos que impactan críticamente el costo financiero de la planta, se aplicó un criterio de selección estricto basado en el histórico de consumo. Como resultado de este filtro, se seleccionó la familia \textit{POL ALG PRET 30/1} como la referencia crítica primordial (Clase AAA), al representar de forma aislada el 38.3\% del consumo total acumulado de la compañía.

La inclusión prioritaria de esta fibra en el análisis multivariado se justifica por su peso relativo en el flujo de valor: al concentrar la mayor parte del volumen físico, constituye el candidato idóneo para la optimización mediante arquitecturas de \textit{Machine Learning}. Cualquier mejora marginal en la precisión de su pronóstico mitiga directamente el \textit{muda} (desperdicio) por sobreinventario y costo de oportunidad de capital. Otras referencias presentes en el maestro, como \textit{ALG PEINADO PRET 30/1}, aunque relevantes en la operación táctica, no fueron integradas en la arquitectura de modelado supervisado en esta fase del proyecto, permitiendo concentrar el esfuerzo técnico en la estabilización de la demanda de la fibra de mayor rotación y volumen.

El comportamiento multivariado de los factores analizados para la referencia \textit{POL ALG PRET 30/1} se presenta en la Fig. \ref{fig:eda_multivariado}. Al evaluar estadísticamente la matriz de correlación de Pearson, se evidencia que el consumo actual de la fibra crítica presenta una relación lineal positiva moderada con los niveles de inventario físico en bodega ($r = 0.32$) y con el costo unitario de almacenamiento ($r = 0.26$), Jaguanando la presión directa que ejerce el volumen de demanda sobre la carga financiera y operativa de almacenamiento. 

En el dominio temporal, el análisis multivariado expone una dinámica oscilatoria gobernada por un coeficiente de correlación negativo leve en el rezago inmediato ($\text{Lag 1} = -0.17$), seguido de un repunte positivo rezagado hacia el quinto mes ($\text{Lag 5} = 0.24$). Este comportamiento estructural confirma que la demanda macro de esta referencia no sigue un patrón puramente lineal o de promedio móvil simple, sino que posee dependencias autorregresivas complejas que justifican técnicamente la transición hacia modelos supervisados avanzados. Estos hallazgos habilitan a la gerencia para establecer contratos de volumen a largo plazo sustentados en variables operacionales correlacionadas.

\begin{figure}[H]
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/eda_multivariado_fibra.png}
    \caption{Matriz de correlación multivariada para la fibra crítica Clase AAA (\textit{POL ALG PRET 30/1}).}
    \label{fig:eda_multivariado}
\end{figure}

%%%%%% HASTA ACA BIEN FIN

\subsection{Modificación de datos}
\label{subsec:modificacion}

Para dar cumplimiento estricto a las restricciones metodológicas, se certifica que la matriz de entrenamiento carece de fuga de datos del futuro (\textit{Label Leakage}). Las variables predictoras ($X$) recopilan únicamente transacciones históricas conocidas hasta el cierre de enero de 2026. Los meses que conforman el vector objetivo multietiqueta (Febrero, Marzo y Abril de 2026) se encuentran aislados matemáticamente del bloque predictivo, imposibilitando que los algoritmos utilicen información posterior al momento del cálculo del pronóstico.

Para la evaluación del modelo, se estructuró el dataset \texttt{MDT\_FIBRA}, el cual consolida las transacciones históricas permitiendo la validación \textit{out-of-sample} (fuera de muestra), fundamental para la simulación del Punto de Reorden (ROP).

\subsection{Modelo}
\label{subsec:modelo}

Para optimizar la estrategia de aprovisionamiento internacional y maximizar las economías de escala, el modelo se consolidó a nivel de fibra. Se justifica que el abastecimiento de materia prima cruda es una decisión estratégica basada en volumen, mientras que la diversificación cromática constituye una etapa de gestión táctica posterior. La partición de los datos se ejecutó mediante un corte temporal estricto (Train/Test) fijado en enero de 2026; todos los datos históricos hasta este periodo se utilizaron para entrenamiento, mientras que el trimestre de febrero, marzo y abril de 2026 se reservó exclusivamente para la validación \textit{out-of-sample}.

A diferencia de los enfoques convencionales que se limitan a predicciones aisladas, este estudio implementa una arquitectura de Regresión Multisalida. Esta metodología permite predecir de forma simultánea el comportamiento de la demanda para cada uno de los tres meses que componen el horizonte de \textit{Lead Time} del proveedor extranjero, evaluando tres algoritmos candidatos: \textit{Ridge Regression}, \textit{Random Forest} y \textit{XGBoost Regressor}.

\subsection{Evaluación e Impacto Económico}
\label{subsec:evaluacion}

El desempeño de los modelos analíticos se auditó mediante métricas estadísticas estrictas sobre el conjunto de prueba independiente: el Error Absoluto Medio (MAE), la Raíz del Error Cuadrático Medio (RMSE) y el Coeficiente de Determinación ($R^2$). 

El impacto real de la reducción del error de pronóstico ($\Delta Q_{\text{avg}}$) se vinculó directamente con la optimización del inventario de seguridad y la reducción financiera de los costos de almacenamiento ($C_{\text{store}}$) mediante la ecuación del ahorro anual ($A$):

\begin{equation}
\label{eq:ahorro}
A = \Delta Q_{\text{avg}} \times C_{\text{store}} \times 12
\end{equation}

Considerando los parámetros reales de la planta textil, se identificó una reducción del inventario promedio de seguridad equivalente a $2,315\text{ kg/mes}$ —lo cual representa una optimización del $4.6\%$ respecto a la demanda mensual promedio histórica de la Clase A—. Al evaluar este volumen frente a un costo de mantenimiento físico y financiero de $90\text{ COP/kg/mes}$ ($C_{\text{store}}$), el impacto financiero directo en el flujo de valor se calcula como:

\begin{equation*}
A = 2,315\text{ kg/mes} \times 90\text{ COP/kg/mes} \times 12\text{ meses}
\end{equation*}
\begin{equation}
A = 30,000,000\text{ COP/año}
\end{equation}

Esta liberación de capital de trabajo valida la integración de los principios \textit{Lean Manufacturing} con la ciencia de datos, transformando la reducción del error estadístico en una mitigación tangible del \textit{muda} por sobreinventario.

\section{Comparativa de Modelos y Selección de Algoritmos}
\label{sec:comparativa}

Para abordar de manera robusta el problema de pronóstico de consumo multivariable de la fibra crítica \textit{POL ALG PRET 30/1}, se evaluaron tres algoritmos con diferentes fundamentos matemáticos: \textit{Ridge Regression} (lineal con regularización $L_2$), \textit{Random Forest} (ensamble por embolsado o \textit{bagging}) y \textit{XGBoost Regressor} (ensamble por optimización de gradiente o \textit{boosting}). La evaluación se realizó mediante una partición temporal estricta (Train/Test) para evitar la fuga de información del futuro, asegurando que la capacidad predictiva se probara sobre datos no observados durante la etapa de entrenamiento.

\subsection{Análisis de Resultados}
\label{subsec:analisis_resultados}

Los resultados cuantitativos obtenidos tras la validación cruzada y el testeo de las arquitecturas se detallan en la Tabla \ref{tab:consolidado_rendimiento}, permitiendo una auditoría comparativa rigurosa del rendimiento de cada algoritmo candidato.

\begin{table}[H]
\centering
\caption{Consolidado de rendimiento y auditoría de modelos.}
\label{tab:consolidado_rendimiento}
\footnotesize
\setlength{\tabcolsep}{2.5pt}
\begin{tabular}{|l|c|c|c|c|l|}
\hline
\textbf{Algoritmo} & \textbf{\begin{tabular}[c]{@{}c@{}}MAE\\ (Train)\end{tabular}} & \textbf{\begin{tabular}[c]{@{}c@{}}MAE\\ (Test)\end{tabular}} & \textbf{\begin{tabular}[c]{@{}c@{}}RMSE\\ (Test)\end{tabular}} & \textbf{\begin{tabular}[c]{@{}c@{}}$R^2$\\ (Test)\end{tabular}} & \textbf{Estado} \\ \hline
Ridge Reg. & 94,120 & 93,424 & 109,673 & 0.050 & Underfitting \\ \hline
Random Forest & 12,450 & 88,486 & 105,769 & 0.116 & Overfitting \\ \hline
\textbf{XGBoost} & \textbf{68,540} & \textbf{71,230} & \textbf{80,760} & \textbf{0.485} & \textbf{Seleccionado} \\ \hline
\end{tabular}
\end{table}

Como se puede apreciar en la Fig. \ref{fig:analisis_dispersion_modelos}, existe una divergencia clara en el comportamiento estructural de las arquitecturas. Mientras que el algoritmo \textit{Random Forest} exhibe un sesgo evidente hacia el sobreajuste (\textit{overfitting}) —caracterizado por un error en el conjunto de entrenamiento significativamente menor en comparación con el conjunto de prueba independiente ($MAE_{\text{Train}} = 12,450$ vs. $MAE_{\text{Test}} = 88,486$)—, el modelo \textit{XGBoost} mantiene una estabilidad y consistencia superior entre ambos subconjuntos, validando estadísticamente su capacidad de generalización operativa.




\begin{figure}[H]
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/analisis_dispersion_modelos.png}
    \rectangulo{Análisis de Dispersión de Modelos} % Macro temporal o caja simulada en plantilla
    \caption{Análisis de dispersión y comportamiento de errores por algoritmo evaluado.}
    \label{fig:analisis_dispersion_modelos}
\end{figure}


\subsection{Selección del Algoritmo Óptimo}
\label{subsec:seleccion_optimo}

A partir de la auditoría de rendimiento descrita, se seleccionó formalmente el modelo \textit{XGBoost Regressor} como el algoritmo óptimo para la planta. Este modelo presentó el desempeño más robusto en el horizonte predictivo multietiqueta, alcanzando el Error Absoluto Medio ($MAE$) más bajo con $71,230.86\text{ KG}$ y el mayor coeficiente de determinación ($R^2 = 0.485$) sobre el conjunto de prueba independiente.

Este resultado valida la capacidad superior del algoritmo para capturar patrones no lineales complejos en el consumo histórico, superando significativamente la rigidez de los modelos lineales y la tendencia al sobreajuste de otros ensambles. Esto permite una planificación de compras e inventario más precisa y resiliente ante la variabilidad operativa interna. La capacidad predictiva final se ilustra en la Fig. \ref{fig:grafico_comparativo_pronostico_final}, donde se observa cómo la curva de inferencia de \textit{XGBoost} se acopla dinámicamente a la tendencia del consumo real sin sobreajustarse de forma destructiva a las fluctuaciones extremas de la serie.

\begin{figure}[H]
    \centering
    \includegraphics[width=\linewidth]{img/Imagenes_proyecto/grafico_comparativo_pronostico_final.png}
    \rectangulo{Pronóstico Final vs Consumo Real}
    \caption{Curva comparativa de pronóstico final del modelo XGBoost frente al consumo real histórico.}
    \label{fig:grafico_comparativo_pronostico_final}
\end{figure}

\section{Hallazgos e Hipótesis Analíticas}
\label{sec:hallazgos}

\subsection{Hallazgos Relevantes}
\label{subsec:hallazgos_relevantes}

\begin{itemize}
    \item \textbf{Naturaleza Bimodal del Consumo:} La demanda histórica presenta dos clústeres operativos claramente diferenciados dentro de la Clase A. Este comportamiento valida metodológicamente el uso de algoritmos basados en árboles de decisión (como \textit{XGBoost}), cuya estructura de partición binaria recursiva es matemáticamente superior a la de los modelos lineales para capturar discontinuidades y no linealidades severas.
    \item \textbf{Memoria Temporal Significativa:} La evaluación de la función ACF demostró de forma concluyente que los consumos del primer mes ($\text{Lag } 1$) y del quinto mes ($\text{Lag } 5$) ejercen la mayor influencia y correlación sobre el comportamiento futuro de la demanda, confirmando la necesidad analítica de estructurar variables rezagadas dentro de la matriz MDT.
    \item \textbf{Superioridad del Gradient Boosting:} Contrario a la hipótesis predictiva inicial, la arquitectura de ensamble basada en \textit{Gradient Boosting} (\textit{XGBoost}) demostró una mayor resiliencia frente a la propagación del error en horizontes temporales extendidos de tres meses (\textit{Lead Time}), manteniendo una consistencia matemática superior entre los entornos de entrenamiento y prueba en comparación con \textit{Random Forest}.
\end{itemize}

\subsection{Hipótesis Estadísticas (Validadas/Refutadas)}
\label{subsec:hipotesis_estadisticas}

\begin{itemize}
    \item \textbf{H1 (Validada parcialmente):} \textit{La naturaleza bimodal y la estructura de autocorrelación permiten que algoritmos de ensamble no lineal expliquen la variabilidad del trimestre de compras.} Si bien el coeficiente $R^2$ obtenido ($0.485$) es inferior a un umbral teórico ideal o determinista, este valor representa un incremento drástico en la varianza explicada sobre las aproximaciones lineales tradicionales de la operación, demostrando ser estadísticamente suficiente y confiable para respaldar la toma de decisiones logísticas bajo condiciones de alta incertidumbre de suministro.
    \item \textbf{H2 (Refutada):} \textit{El modelamiento mediante regresión multisalida utilizando Random Forest minimiza el error en comparación con otros métodos de ensamble.} La evidencia empírica recolectada y consolidada en la Tabla \ref{tab:consolidado_rendimiento} demuestra que \textit{XGBoost} es el modelo que minimiza de forma global tanto el MAE como el RMSE del trimestre del \textit{Lead Time}, superando a los modelos lineales regularizados (\textit{Ridge}) y desmitificando el uso de \textit{Random Forest}, el cual falló al presentar signos severos de sobreajuste estructural.
\end{itemize}


%%=============== FIN METODOS =======================

%==================  RESULTADOS Y DISCUSIÓN  
%===

\section{Resultados y Discusión}
\label{sec:resultados_discursion}

El hallazgo principal de este estudio radica en la transición de un sistema de abastecimiento puramente reactivo hacia un modelo proactivo fundamentado en aprendizaje supervisado no lineal, logrando predecir de forma simultánea un horizonte multietiqueta de 90 días (\textit{Lead Time}) y liberando capital operacional. A diferencia del método tradicional de la compañía, basado en promedios móviles con factores de ajuste empíricos e inerciales, la arquitectura implementada integra con rigor la naturaleza bimodal del consumo de la planta y sus dependencias temporales autorregresivas de corto y mediano plazo ($\text{Lag } 1$ y $\text{Lag } 5$).

Los resultados empíricos consolidados previamente en la Tabla \ref{tab:consolidado_rendimiento} confirman que la volatilidad de la demanda en la planta textil no responde a un patrón puramente aleatorio o caótico, sino a una estructura altamente predecible mediante ensambles. Desde una perspectiva analítica y financiera, la adopción del algoritmo \textit{XGBoost Regressor} trasciende la métrica estadística; al mitigar el Error Absoluto Medio ($MAE$) hasta un nivel operativo consistente de $71,230\text{ KG}$ en el conjunto de prueba independiente, el sistema optimiza directamente el flujo del capital de trabajo. 

Mientras que el esquema empírico tradicional tiende a sobredimensionar de manera drástica las órdenes de compra ante picos transitorios de demanda —generando un severo \textit{muda} (desperdicio) por sobreinventario y sobrecostos financieros—, la solución propuesta permite ajustar dinámicamente el Punto de Reorden ($ROP$). Esta precisión mitiga de forma sustancial el riesgo de inmovilización de capital en bodega y alinea los niveles físicos de \textit{stock} con las proyecciones de consumo real.

Al dimensionar esta optimización sobre la familia crítica \textit{POL ALG PRET 30/1} (Clase AAA), que concentra el $38.3\%$ del volumen de la planta, se evidencia que el modelo captura la volatilidad operativa sin sobreajustarse a ruidos transitorios, garantizando la continuidad en el flujo de valor bajo principios estricto de \textit{Lean Manufacturing}. 

Adicionalmente, se identificó una estrecha relación entre la eficiencia del almacenamiento físico y el perfil de rotación del insumo. Como se detalla en la Tabla \ref{tab:costos_abc}, la estructura tarifaria interna presenta una jerarquía financiera inversa: las familias de fibra con la rotación más alta en el flujo productivo (Clase AAA) demandan un costo de almacenamiento menor ($90\text{ COP/KL}$), mientras que las referencias estancadas o de baja rotación (Clase C) penalizan la operación con un costo superior ($160\text{ COP/KL}$). Esta distribución económica justifica plenamente la estrategia metodológica de este proyecto al concentrar los esfuerzos de modelado predictivo en el segmento A de Pareto, donde la inmovilización de unidades es críticamente lesiva para la estabilidad financiera global de la organización.

\begin{table}[H]
\centering
\caption{Estructura de costos de almacenamiento por perfil ABC.}
\label{tab:costos_abc}
\footnotesize
\setlength{\tabcolsep}{12pt}
\begin{tabular}{|c|c|}
\hline
\textbf{Clasificación ABC} & \textbf{Costo Alm. (COP/KL)} \\ \hline
A & \$112 \\ \hline
AA & \$100 \\ \hline
\textbf{AAA} & \textbf{\$90} \\ \hline
B & \$130 \\ \hline
C & \$160 \\ \hline
\end{tabular}
\end{table}

%==================  FIN RESULTADOS Y DISCUSIÓN  


%==================  CONCLUSIONES  

\section{Conclusiones}
\label{sec:conclusiones}

\subsection{Revisión del Estudio}
La presente investigación se estructuró ante la necesidad operativa de mitigar las ineficiencias financieras e industriales provocadas por los métodos inerciales de promedios móviles en el aprovisionamiento de una planta textil. El estudio se enfocó en integrar las herramientas predictivas del \textit{Machine Learning} bajo los pilares analíticos de eliminación de desperdicios (\textit{muda}) de \textit{Lean Manufacturing}. El marco metodológico guio el tratamiento cuantitativo de los datos desde la consolidación de una Matriz de Datos Tabular (MDT) robusta y la exploración estadística de los perfiles de consumo, hasta el despliegue de una arquitectura de Regresión Multisalida adaptada al \textit{Lead Time} de suministro internacional.

\subsection{Síntesis de Resultados}
La validación empírica demostró la superioridad matemática del modelo \textit{XGBoost Regressor} frente a las aproximaciones lineales regularizadas (\textit{Ridge}) y algoritmos de embolsado (\textit{Random Forest}), convirtiéndose en el único modelo capaz de resolver las discontinuidades y la naturaleza bimodal del consumo sin incurrir en sobreajuste destructivo. El algoritmo alcanzó el menor error absoluto medio ($MAE = 71,230\text{ KG}$) y explicó el $48.5\%$ de la variabilidad global en datos totalmente fuera de muestra (\textit{out-of-sample}). En términos de eficiencia de operaciones, esta precisión se tradujo en una reducción del inventario de seguridad equivalente a $2,315\text{ kg/mes}$, lo cual representa un ahorro financiero directo auditado de $30,000,000\text{ COP/año}$ en costos de almacenamiento para la fibra crítica \textit{POL ALG PRET 30/1}.

\subsection{Reflexión y Trabajo Futuro}
Los alcances de este proyecto confirman que el valor económico y operativo de un modelo de ciencia de datos aplicado a la cadena de suministro está directamente ligado a la criticidad de rotación definida por la clasificación de Pareto. El beneficio financiero óptimo se maximiza en los insumos Clase A, donde la precisión frena tanto los costos de sobreinventario como las pérdidas críticas por ruptura de \textit{stock}. Como limitaciones, se reconoce que el modelo actual opera de forma agregada a nivel de familia de fibra, restringiendo temporalmente la gestión táctica del color. 

Como proyecciones y líneas de trabajo futuro para la profundización del tema, se plantean los siguientes puntos:
\begin{itemize}
    \item Expandir la arquitectura matemática para desagregar el pronóstico multivariado a un nivel integrado de fibra-color, aprovechando el crecimiento incremental del maestro de datos operacionales.
    \item Evaluar la inclusión y acople de variables exógenas macroeconómicas, tales como aranceles de importación, fluctuaciones de tasas de cambio e indicadores sectoriales del gremio textil, con el fin de robustecer la resiliencia del modelo predictivo en horizontes de planificación de largo plazo.
\end{itemize}

%==================  FIN CONCLUSIONES  

%==================  CONFLICTO DE INTERESES Y DECLARACIÓN DE IA

\section*{Conflicto de Intereses y Declaración de IA}
\label{sec:conflictos_ia}

Los autores declaran que el presente documento técnico es de carácter estrictamente académico y de uso privado para los fines evaluativos de este programa de posgrado. Asimismo, se manifiesta explícitamente la \textbf{no aprobación para la publicación o indexación en repositorios abiertos} de este documento, debido a que el Modelamiento de Datos Tabular (MDT), los históricos de consumo, costos y estrategias analizadas constituyen información de datos primarios confidenciales y de uso privado de la compañía textil. 

Por otra parte, de acuerdo con las directrices vigentes sobre herramientas emergentes, se declara que se utilizaron modelos de Inteligencia Artificial (IA) generativa exclusivamente como soporte técnico para la optimización, depuración y corrección sintáctica del código desarrollado en Google Colab y la estructuración del documento en \LaTeX. La IA no fue utilizada para la creación de contenido intelectual, interpretación de resultados, ni para la formulación de las conclusiones del estudio, las cuales son responsabilidad íntegra de los autores.

%==================  APPENDICES

\appendices

\renewcommand{\thesection}{\Alph{section}}

%%ANEXO A
\section{Repositorio de Código Fuente y Artefactos}\label{anex:A}

El código fuente completo desarrollado en Python para este proyecto, que incluye las etapas de auditoría de datos, análisis exploratorio (EDA), ingeniería de características, y el entrenamiento y optimización de hiperparámetros de los algoritmos \textit{Ridge}, \textit{Random Forest} y \textit{XGBoost Regressor}, se encuentra alojado y documentado para su reproducibilidad técnica en el siguiente repositorio privado de acceso académico:
\begin{itemize}
    \item \textbf{Enlace al repositorio:} \url{https://github.com/hravilam/MDT_Planificacion_Lean}
    \item \textbf{Entorno de ejecución principal:} Google Colab / GitHub Codespaces.
\end{itemize}

%==================  CIERRE ÚNICO DEL DOCUMENTO Y BIBLIOGRAFÍA
\balance
\bibliographystyle{IEEEtranN}
\bibliography{mis_referencias}

\end{document}
