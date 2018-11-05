---
title: Publicar la base de datos de ubicación desde Lync Server 2013
TOCTitle: Publicar la base de datos de ubicación desde Lync Server 2013
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48276884
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicar la base de datos de ubicación desde Lync Server 2013

 

_**Última modificación del tema:** 2012-10-30_

Las nuevas ubicaciones agregadas a la base de datos de ubicaciones no estarán disponibles para el cliente mientras no se hayan publicado.

Para más información, vea la documentación de Shell de administración de Lync Server para el siguiente cmdlet:

  - **Publish-CsLisConfiguration**

Si usa puertas de enlace de número de identificación de ubicación de emergencia (ELIN), cargue también los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC). Probablemente el proveedor de RTC le solicite que use un formato específico para los registros de ELIN. Póngase en contacto con el proveedor de RTC para más información. Exporte los registros de la base de datos de Servicio de información de ubicaciones y asígneles el formato necesario.

## Para publicar la base de datos de ubicaciones

  - Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

  - Ejecute el cmdlet siguiente para publicar la base de datos de ubicaciones.
    
        Publish-CsLisConfiguration

