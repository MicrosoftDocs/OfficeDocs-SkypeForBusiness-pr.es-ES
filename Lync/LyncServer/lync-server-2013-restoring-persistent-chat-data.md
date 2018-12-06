---
title: Restaurar datos de chat persistente
TOCTitle: Restaurar datos de chat persistente
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945649(v=OCS.15)
ms:contentKeyID: 52061734
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar datos de chat persistente

 

_**Última modificación del tema:** 2013-02-18_

El contenido del salón del Chat persistente se almacena en la base de datos de Chat persistente (Mgc.mdf). Se trata de los datos importantes para el negocio de los que se debe hacer una copia de seguridad cada cierto tiempo. Aparte del contenido del salón de chat, en la base de datos del Chat persistente también se almacenan las entidades de seguridad (como los usuarios y grupos de usuarios) y los roles y el acceso que tienen a los salones de chat y a su contenido.

El modo en que se restauren los datos del Chat persistente dependerá del método que se haya empleado para hacer la copia de seguridad.

  - Si se han usado los procedimientos de copia de seguridad de SQL Server, se deberá recurrir a los procedimientos de restauración de SQL Server correspondientes.

  - Si se usó el cmdlet **Export-CsPersistentChatData** para realizar la copia de seguridad de los datos del Chat persistente, se deberá usar el cmdlet **Import-CsPersistentChatData** para restaurar los datos.

