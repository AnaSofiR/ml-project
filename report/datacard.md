# Data Card — California Housing Dataset

## Información general
| Campo        | Detalle                                              |
|--------------|------------------------------------------------------|
| Nombre       | California Housing Dataset                           |
| Fuente       | Pace, R.K. y Barry, R. (1997). Sparse Spatial        |
|              | Autoregressions. Statistics & Probability Letters.  |
| Acceso       | sklearn.datasets.fetch_california_housing()          |
| Año          | Censo de California, 1990                            |
| Registros    | 20,640 distritos censales                            |
| Variables    | 8 features + 1 target                                |
| Valores nulos| Ninguno                                              |
| Tipo de tarea| Regresión supervisada                                |
| Licencia     | Dominio público                                      |

## Variables

| Variable     | Tipo      | Unidades              | Rango            | Descripción                              |
|--------------|-----------|-----------------------|------------------|------------------------------------------|
| MedInc       | Continua  | Decenas de miles USD  | 0.5 – 15.0       | Ingreso mediano del hogar                |
| HouseAge     | Continua  | Años                  | 1 – 52*          | Edad mediana de viviendas del bloque     |
| AveRooms     | Continua  | Habitaciones/hogar    | 0.8 – 141.9*     | Promedio de habitaciones por hogar       |
| AveBedrms    | Continua  | Dormitorios/hogar     | 0.3 – 34.1*      | Promedio de dormitorios por hogar        |
| Population   | Continua  | Personas              | 3 – 35,682       | Población del bloque censal              |
| AveOccup     | Continua  | Ocupantes/hogar       | 0.7 – 1,243.3*   | Promedio de ocupantes por hogar          |
| Latitude     | Continua  | Grados                | 32.5 – 42.0      | Latitud del bloque censal                |
| Longitude    | Continua  | Grados                | -124.4 – -114.3  | Longitud del bloque censal               |
| MedHouseVal  | Continua  | USD                   | $15,000–$500,001*| **TARGET** Valor mediano de vivienda     |

*Variables con truncamiento o outliers extremos (ver sección de limitaciones)

## Limitaciones y riesgos potenciales

### Truncamientos conocidos
- **MedHouseVal**: valores superiores a $500,000 están registrados como
  $500,001 (~4.8% de los registros). El modelo subestimará
  sistemáticamente viviendas de alto valor.
- **HouseAge**: viviendas con más de 52 años aparecen todas como 52.

### Outliers extremos
- **AveRooms** (max 141.9) y **AveBedrms** (max 34.1): corresponden
  a hoteles u hostales incluidos en el censo, no a viviendas
  residenciales típicas.
- **AveOccup** (max 1,243): valores anómalos que requieren tratamiento
  antes del modelado.

### Limitaciones de contexto
- Los datos son de 1990 y no reflejan el mercado inmobiliario actual.
- Las variables son agregados a nivel de bloque censal, no de
  vivienda individual. No hay información sobre estado de la vivienda,
  renovaciones, o características internas.
- Sesgo geográfico: el dataset solo cubre California.

### Riesgos para el modelado
- La multicolinealidad entre AveRooms y AveBedrms (r=0.85) puede
  causar inestabilidad en modelos lineales.
- La multicolinealidad entre Latitude y Longitude (r=-0.92) debe
  tenerse en cuenta al interpretar coeficientes.
- El truncamiento en $500,001 introduce sesgo sistemático en el
  extremo superior que ningún modelo puede corregir sin información
  adicional.