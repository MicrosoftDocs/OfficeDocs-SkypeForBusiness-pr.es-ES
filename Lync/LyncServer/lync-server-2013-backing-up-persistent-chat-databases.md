---
title: Copia de seguridad de las bases de datos de chat persistente
TOCTitle: Copia de seguridad de las bases de datos de chat persistente
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945646(v=OCS.15)
ms:contentKeyID: 52061759
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Copia de seguridad de las bases de datos de chat persistente

 

_**Última modificación del tema:** 2013-02-17_

El contenido del salón del Chat persistente se almacena en la base de datos de Chat persistente (Mgc.mdf). Se trata de los datos importantes para el negocio de los que se debe hacer una copia de seguridad cada cierto tiempo. Aparte del contenido del salón de chat, en la base de datos del Chat persistente también se almacena información sobre las entidades de seguridad (como los usuarios y grupos de usuarios) y los roles y el acceso que tienen a los salones de chat.

Existen dos formas de hacer una copia de seguridad de los datos del Chat persistente.

  - Copia de seguridad de SQL Server

  - El cmdlet `Export-CsPersistentChatData`, con el que los datos del Chat persistente se exportan como un archivo

Si bien los datos que se crean con la copia de seguridad de SQL Server necesitan un espacio en disco notablemente mayor (hasta 20 veces más) que los creados con `Export-CsPersistentChatData`, lo más seguro es que los administradores estén más familiarizados con el primer procedimiento.

