---
title: "Tiempo de recuperación para conmut. error y recuperación grupo de servidores"
TOCTitle: Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48276013
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-10_

Para conmutación por error y conmutación por recuperación de grupos de servidores, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 30 minutos. Este es el tiempo necesario para que tenga lugar la conmutación por error, una vez que el administrador ha determinado que se ha producido un desastre e inicia los procedimientos de conmutación por error. No incluye el tiempo necesario para que el administrador evalúe la situación y tome una decisión, como tampoco el tiempo necesario para que los usuarios vuelvan a iniciar sesión una vez que finalice la conmutación por error.

Para conmutación por error y conmutación por recuperación de grupos de servidores, el objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 30 minutos. Esto representa la medición de tiempo de los datos que se podría perder debido a un desastre, debido a la latencia de replicación del Servicio de copia de seguridad. Por ejemplo, si un grupo de servidores deja de estar activo a las 10:00 A.M. y el RPO es de 30 minutos, los datos escritos en el grupo de servidores entre las 9:30 A.M. y las 10:00 A.M.podrían no haberse replicado en el grupo de servidores de copia de seguridad y podrían haberse perdido.

En todos los números de RTO y RPO de este documento se asume que los dos centros de datos se encuentran en la misma región del mundo con un transporte de alta velocidad y baja latencia entre las dos ubicaciones. Estos números se miden para un grupo de usuarios con 40.000 usuarios activos simultáneamente y 200.000 usuarios habilitados para Lync con respecto a un modelo de usuario predefinido en el que no hay trabajo pendiente en la replicación de datos. Están sujetos a cambios a partir de las pruebas de rendimiento y validación.

