---
title: 'Lync Server 2013: control remoto de llamadas y normalización de números de teléfono'
description: 'Lync Server 2013: control remoto de llamadas y normalización de números de teléfono.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555816"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Control remoto de llamadas y normalización de números de teléfono en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Los clientes de Lync descargan reglas de normalización de números de teléfono como parte de la descarga de archivos del servicio de libreta de direcciones (ABS). En los escenarios de control remoto de llamadas, las reglas de normalización de número de teléfono del servicio de libreta de direcciones se aplican a las llamadas entrantes y salientes del control remoto de llamadas. Para las llamadas entrantes a un usuario habilitado para el control remoto de llamadas, el número de teléfono del autor de la llamada se normaliza primero al formato E. 164 mediante la puerta de enlace SIP/CSTA o central de conmutación (PBX). Cuando Lync Server 2013 recibe la llamada de la puerta de enlace, realiza una búsqueda inversa de números (RNL) en el número de teléfono del autor de la llamada en el número normalizado de la lista de contactos de Microsoft Office Outlook del destinatario de la llamada o en la lista global de direcciones (GAL) que se almacena en el servicio de libreta de direcciones. Si la búsqueda de números inversas encuentra una coincidencia, el autor de la llamada se identifica por su nombre en la notificación de llamada entrante.

Para las llamadas de control remoto de llamadas salientes, Lync aplica las reglas de normalización de números de teléfono del servicio de libreta de direcciones al número marcado antes de enrutar la llamada a la puerta de enlace SIP/CSTA.

Para obtener información detallada sobre cómo crear reglas de normalización de números de teléfono para el control remoto de llamadas, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación referente a la planeación.

<div>

## <a name="migrating-phone-number-normalization-rules"></a>Migración de reglas de normalización de números de teléfono

Si va a migrar usuarios habilitados previamente para control remoto de llamadas, consulte los siguientes temas en la documentación sobre migración:

  - Para Lync Server 2010, consulte [Migrate Address Book](migrate-address-book.md) en la documentación de migración.

  - Para Communications Server 2007 R2, consulte [Migrate Address Book](migrate-address-book.md) en la documentación de migración.

</div>

</div>

<span> </span>

</div>

</div>

</div>

