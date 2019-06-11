---
title: 'Lync Server 2013: Control remoto de llamadas y normalización de números de teléfono'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Control remoto de llamadas y normalización de números de teléfono en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Los clientes de Lync descargan reglas de normalización de números de teléfono como parte de la descarga de archivos del servicio de libreta de direcciones (ABS). En los escenarios de control remoto de llamadas, las reglas de normalización de números de teléfono del servicio de libreta de direcciones se aplican a las llamadas entrantes y salientes de control remoto de llamadas. Para las llamadas entrantes a un usuario con control de llamadas remoto, el número de teléfono de la persona que llama se normaliza primero al formato E. 164 por la puerta de enlace SIP/CSTA o por la central de conmutación (PBX). Cuando Lync Server 2013 recibe la llamada de la puerta de enlace, realiza una búsqueda de números invertida (RNL) en el número de teléfono del autor de la llamada en relación con el número normalizado en la lista de contactos de Microsoft Office Outlook de la llamada o la lista global de direcciones (GAL) almacenada en el servicio de libreta de direcciones. Si la búsqueda de números inversas encuentra una coincidencia correctamente, la persona que llama se identifica por el nombre en la notificación de llamada entrante.

Para las llamadas de control remoto de llamadas salientes, Lync aplica las reglas de normalización de números de teléfono del servicio de libreta de direcciones al número marcado antes de enrutar la llamada a la puerta de enlace SIP/CSTA.

Para obtener detalles sobre la creación de reglas de normalización de números de teléfono para el control remoto de llamadas, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de planeación.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migrar reglas de normalización de números de teléfono

Si va a migrar usuarios previamente habilitados para el control remoto de llamadas, consulte los siguientes temas en la documentación de la migración:

  - Para Lync Server 2010, consulte [migrar la libreta de direcciones](migrate-address-book.md) en la documentación de la migración.

  - Para Communications Server 2007 R2, consulte [migrar la libreta de direcciones](migrate-address-book_1.md) en la documentación de la migración.

</div>

</div>

<span> </span>

</div>

</div>

</div>

