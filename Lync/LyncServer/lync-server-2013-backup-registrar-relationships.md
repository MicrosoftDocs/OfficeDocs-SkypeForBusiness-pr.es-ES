---
title: Relaciones del registrador de copia de seguridad en Lync Server 2013
TOCTitle: Relaciones del registrador de copia de seguridad
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48275801
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Relaciones del registrador de copia de seguridad en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-28_

Además de proporcionar la capacidad de recuperación ante desastres, dos grupos de servidores emparejados sirven como registradores de copia de seguridad entre sí. En Lync Server 2013, las relaciones de registrador de copia de seguridad entre Grupos de servidores front-end siempre son 1:1 y recíprocas. Esto significa que, si P1 es la copia de seguridad de P2, entonces P2 deberá ser la copia de seguridad de P1, y ninguna de ellas podrá ser la copia de seguridad de ningún otro grupo de servidores front-end. Esto es un cambio respecto a Lync Server 2010, donde las relaciones de copia de seguridad de los Grupo de servidores front-end podían ser de varios a uno.

Aunque las relaciones de copia de seguridad entre dos Grupos de servidores front-end deba ser 1:1 y simétricas, cada Grupo de servidores front-end sigue pudiendo ser el registrador de copia de seguridad de cualquier número de Aplicaciones de sucursal con funciones de supervivencia, igual que sucedía en Lync Server 2010.

Tenga en cuenta que Lync Server 2013 no amplía la capacidad de recuperación ante desastres para usuarios hospedados en una Aplicación de sucursal con funciones de supervivencia. Si un grupo de servidores front-end que sirve como copia de seguridad de una Aplicación de sucursal con funciones de supervivencia deja de estar disponible, los usuarios que hayan iniciado sesión en la aplicación Aplicación de sucursal con funciones de supervivencia caerán al modo de resistencia incluso después de que los usuarios hospedados en el grupo de servidores front-end hayan conmutado por error al Grupo de servidores front-end de copia de seguridad.

