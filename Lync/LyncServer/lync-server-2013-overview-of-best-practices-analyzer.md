---
title: Introducción del Analizador de procedimientos recomendados
TOCTitle: Introducción del Analizador de procedimientos recomendados
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48276625
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción del Analizador de procedimientos recomendados

 

_**Última modificación del tema:** 2012-09-19_

Puede usar el Analizador de procedimientos recomendados de Lync Server 2013 para identificar y solucionar los problemas que se presenten con la implementación de Lync Server 2013. El Analizador de procedimientos recomendados de Lync Server 2013 recopila información de configuración de los componentes de Lync Server 2013.

Con el acceso de red adecuado, el Analizador de procedimientos recomendados puede examinar los servidores que ejecuten Servicios de dominio de Active Directory, mensajería unificada de Exchange Server y Lync Server 2013. Puede usar el Analizador de procedimientos recomendados para realizar las acciones siguientes:

  - Efectuar comprobaciones de forma proactiva, que comprueben si la configuración se ha definido según los mejores procedimientos recomendados.

  - Detectar automáticamente las actualizaciones necesarias de Lync Server 2013.

  - Generar una lista de cuestiones, como valores de configuración inferiores a los óptimos, opciones no compatibles, actualizaciones que faltan o procedimientos no recomendados.

  - Ayudar a solucionar problemas y resolver problemas específicos.

El Analizador de procedimientos recomendados dispone de las siguientes características:

  - Requisitos previos de instalación mínimos.

  - Documentación en línea sobre las cuestiones notificadas, como sugerencias para la solución de problemas.

  - Información de configuración que se puede guardar para repasarla posteriormente.

  - Análisis del sistema de última generación.

El Analizador de procedimientos recomendados usa un conjunto de archivos de configuración XML para determinar la información que debe recopilarse del entorno de Lync Server 2013. Además de comprobar los Servicios de dominio de Active Directory, también comprueba orígenes como la configuración y el registro del sistema operativo de Windows Server en Instrumental de administración de Windows (WMI).

El Analizador de procedimientos recomendados compara los datos que recopila con un conjunto de reglas predefinidas para los valores y las configuraciones de las implementaciones de Lync Server 2013.

Después de comparar los datos recopilados con las reglas predefinidas, la herramienta notifica los problemas. Por cada problema que notifica, el Analizador de procedimientos recomendados proporciona información sobre lo que ha detectado en el entorno de Lync Server 2013 que ha explorado, y la configuración recomendada. También proporciona vínculos a información más detallada sobre los problemas específicos.


> [!NOTE]
> El Analizador de procedimientos recomendados de Lync Server 2013 recopila información de configuración solo de los componentes de Lync Server 2013. Puede usar las versiones anteriores de la herramienta para explorar entornos anteriores. Para más información, consulte <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requisitos para la ejecución del Analizador de procedimientos recomendados</A>.


