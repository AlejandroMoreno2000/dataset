# Conjunto de muestras para la captura de trazas electromagnéticas

Este repositorio contiene los binarios empleados para generar trazas electromagnéticas (EM) en el contexto del Trabajo de Fin de Grado (TFG) titulado _"Detección de malware mediante el estudio de la emanación electromagnética"_. Las muestras recopiladas se utilizaron exclusivamente para ejecutar software en un entorno controlado y registrar su comportamiento físico mediante instrumentación externa.

## Contenido

Las muestras incluidas abarcan una amplia variedad de categorías y transformaciones:

- **Malware funcional**: GonnaCry, Mirai, Gafgyt, Troyano.
- **Goodware**: Aplicaciones legítimas utilizadas como referencia para el entrenamiento de modelos.
- **Muestras ofuscadas**: Versiones modificadas mediante técnicas de virtualización, empaquetado, opacidad, división, aplanamiento, y anti-análisis.

> **Nota:** Algunas muestras han sido alteradas específicamente para simular entornos de evasión o representar técnicas avanzadas de ocultación.

## Uso previsto

Este repositorio está destinado exclusivamente a **fines académicos y de investigación**. Su uso está vinculado a la ejecución de software en condiciones controladas, con el objetivo de generar señales EM para su posterior análisis mediante modelos de clasificación basados en Machine Learning y Deep Learning.

## Advertencia de seguridad

**Este repositorio contiene muestras de malware real.**

- No se debe ejecutar ningún archivo fuera de un entorno totalmente **aislado y sin acceso a red** (por ejemplo, máquinas virtuales con snapshot o sandboxes dedicadas).
- La ejecución en entornos no controlados puede comprometer el sistema y poner en riesgo la seguridad de otros dispositivos.
- El autor y la universidad **no se responsabilizan** del uso indebido de los archivos.

## Estructura del repositorio

```plaintext
├── goodware
│   ├── comandos.txt
│   ├── ficheros-auxiliares
│   │   └── texto.txt
│   ├── original
│   │   ├── base64
│   │   ├── cp
│   │   ├── date
│   │   ├── dir
│   │   ├── echo
│   │   ├── env
│   │   ├── printf
│   │   ├── prueba
│   │   └── who
│   ├── proyecto-ejecucion
│   │   └── main.c
│   └── upx
│       ├── cat-upx
│       ├── ls-upx
│       ├── printenv-upx
│       ├── pwd-upx
│       ├── tty-upx
│       ├── uname-upx
│       ├── uptime-upx
│       └── who-upx
└── malware
    ├── ofuscado
    │   ├── antianalysis
    │   │   ├── decryptor
    │   │   ├── gonnacry
    │   │   ├── gonnacry.zip
    │   │   ├── mirai
    │   │   └── mirai.zip
    │   ├── flatten
    │   │   ├── decryptor
    │   │   ├── gonnacry
    │   │   ├── gonnacry.zip
    │   │   ├── mirai
    │   │   └── mirai.zip
    │   ├── opaque
    │   │   ├── decryptor
    │   │   ├── gonnacry
    │   │   ├── gonnacry.zip
    │   │   ├── mirai
    │   │   └── mirai.zip
    │   ├── split
    │   │   ├── decryptor
    │   │   ├── gonnacry
    │   │   ├── gonnacry.zip
    │   │   ├── mirai
    │   │   └── mirai.zip
    │   ├── upx
    │   │   ├── decryptor_camilla_CBC_upx
    │   │   ├── decryptor_upx
    │   │   ├── gafgyt_upx_1
    │   │   ├── gafgyt_upx_2
    │   │   ├── gonnacry_camilla_CBC_upx
    │   │   ├── gonnacry_upx
    │   │   ├── mirai.dbg_upx
    │   │   ├── mirai_upx
    │   │   ├── trojan_upx_1
    │   │   └── trojan_upx_2
    │   └── virtualize
    │       ├── decryptor
    │       ├── gonnacry
    │       ├── gonnacry.zip
    │       ├── mirai
    │       └── mirai.zip
    └── original
        ├── gafgyt
        │   ├── gafgyt_variante_1
        │   ├── gafgyt_variante_2
        │   ├── gafgyt_variante_3
        │   └── gafgyt_variante_4
        ├── gonnacry
        │   ├── Camellia-256-CBC.zip
        │   ├── decryptor
        │   ├── decryptor_Camellia_256_CBC
        │   ├── decryptor_CHACHA20_POLY1305
        │   ├── decryptor_DES_CBC
        │   ├── decryptor_SM4_CBC
        │   ├── gonnacry
        │   ├── gonnacry_Camellia_256_CBC
        │   ├── gonnacry_CHACHA20_POLY1305
        │   ├── gonnacry_CHACHA20_POLY1305.zip
        │   ├── gonnacry_DES_CBC
        │   ├── gonnacry_DES-CBC.zip
        │   ├── gonnacry_SM4_CBC
        │   ├── gonnacry_SM4_CBC.zip
        │   └── gonnacry.zip
        ├── mirai
        │   ├── mirai.dbg
        │   ├── mirai_variante_1
        │   ├── mirai_variante_2
        │   ├── mirai_variante_3
        │   ├── mirai_variante_4
        │   └── mirai.zip
        └── trojan
            ├── trojan_variante_1
            ├── trojan_variante_2
            ├── trojan_variante_3
            ├── trojan_variante_4
            ├── trojan_variante_5
            └── trojan_variante_6

```

## Relación con el sistema de análisis y captura

Este conjunto de muestras está directamente relacionado con los sistemas de captura y análisis desarrollados como parte del proyecto. Existen referencias cruzadas explícitas entre los archivos de este repositorio y los utilizados en:

🔗 [Sistema de análisis y clasificación de trazas EM](https://github.com/AlejandroMoreno2000/analisis)  
🔗 [Sistema de adquisición de señales electromagnéticas](https://github.com/AlejandroMoreno2000/adquisicion-datos)

- En el sistema de **análisis**, las muestras aquí contenidas están mapeadas mediante listas de control denominadas `tagmaps`, que vinculan cada traza con el binario que la generó y su categoría correspondiente (tipo, familia, técnica de evasión...).
- En el sistema de **adquisición**, los archivos incluidos se utilizaron como comandos de entrada (`cmdFile`) para generar las trazas EM, asegurando que la ejecución de cada muestra estuviera correctamente sincronizada con el osciloscopio mediante un wrapper dedicado.

Ambos sistemas están diseñados para reproducir con precisión las condiciones del experimento y permitir la evaluación rigurosa de los modelos de detección.
