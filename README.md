# TFM: Descifrar la red cerebral de la Esclerosis Múltiple mediante grafos y redes neuronales (GNN) aplicadas a neuroimagen multimodal

Estructura:

Code:
- 1_crear_patients.ipynb: Se encarga de crear un archivo con los ID's de pacientes y su origen.
- 2_preprocesamiento.ipynb: Contiene la pipeline de preprocesamiento.
- 3_metricas_grafo.ipynb: Contiene la pipeline encargada de computar las métricas de grafo tanto unilayer como multilayer.
- 4_analisis_metricas_grafo.ipynb: Contiene la pipeline encargada de generar las visualizaciones y análisis estadístico de las métricas de grafo.
- 5_guardar_multigrafos.ipynb: Contiene la pipeline encargada de guardar las matrices de conectividad del multilayer.
- 6_GNNs.ipynb: Contiene la pipeline de entrenamiento de las GNNs y de extracción de información mediante GNNExplainer.

Data:
- DADES_CORRECTED:
  - CLINIC.csv: Contiene la información clínica utilizada en el estudio (contiene solo información referente a la EM y el lugar/protocolo de origen)
  - GM_FA.csv: Contiene el valor de FA para cada región.
  - GM_MD.csv: Contiene el valor de MD para cada región.
  - NODES.csv: Contiene el valor de Volumen para cada región.
  - multi/FA/GM/rsfmri_network: Contiene los archivos {ID_cliente}.csv con las matrices de conectividad de la red referente.

- GNN:
  - GCN_GAT_MULTI.pth: Contiene los pesos del modelo GCN + GAT entrenado para el caso multilayer.
  - avg_node_feature.csv: Contiene la importancia media en la predicción de EM por nodo y feature.
  - avg_edge_importance: Contiene la importancia media en la predicción de EM por conexión.

- METRICAS_GRAFO:
  - {métrica}_{red}_LOCAL.csv: Contiene el valor de la métrica nodal por paciente y nodo.
  - {red}_GLOBAL.csv: Contiene el valor de las métricas globales por paciente.


- Node_mindboggle_default.node: Contiene las coordenadas de cada nodo o región cerebral para su posterior representación.
- patients.csv: Archivo generado a partir de 1_crear_patients.ipynb

En caso de querer ejecutar el preprocesado se ha de cargar una estructura similar a DADES_CORRECTED pero llamados DADES_NAPLES y DADES_HCB.
