---
title: 'Lync Server 2013: Alta disponibilidad del uso compartido de archivos'
TOCTitle: Alta disponibilidad del uso compartido de archivos
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48276456
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Alta disponibilidad del uso compartido de archivos en Lync Server 2013

 

_**Última modificación del tema:** 2012-03-30_

Para asegurar la alta disponibilidad para el uso compartido de archivos de Lync Server dentro de un solo centro de datos, puede usar el Sistema de archivos distribuido (DFS). DFS admite la conmutación por error de un servidor de archivos a otro del mismo centro de datos. Para una implementación a gran escala, recomendamos que use servidores de archivos dedicados que se emparejen mediante DFS.

En función del tamaño de la red y de la cantidad de resistencia que desee, puede usar un par de servidores para hospedar todos los recursos compartidos de archivos de un sitio o usar un par por grupo de servidores front-end.

DFS es un mecanismo de replicación de archivos de tipo “mejor esfuerzo” (best effort), sin ningún compromiso de objetivo de tiempo de recuperación (RTO) ni de objetivo de punto de recuperación (RPO) publicado. La conmutación por error entre los servidores DFS debe realizarse rápidamente, pero el retraso en la replicación de datos puede impedir que los usuarios continúen el trabajo en curso cuando tenga lugar la conmutación por error.

Si usa DFS y el almacén de datos en el recurso compartido de archivos es crítico, debe realizar una copia de seguridad de los usos compartidos de archivos con frecuencia, por ejemplo cada 4 u 8 horas. Si un recurso compartido de archivos deja de estar operativo y la replicación no está actualizada, puede usar la copia de seguridad para restaurar el contenido del servidor que ha fallado en el otro servidor que está emparejado con el servidor que ahora no está disponible.

