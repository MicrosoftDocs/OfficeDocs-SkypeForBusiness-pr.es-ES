---
title: 'Lync Server 2013: configurar el Sign-In de cliente automático para usar el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522967"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a>Configurar el Sign-In de cliente automático para usar el Director en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Al implementar un grupo de directores o un director de Lync Server 2013, se recomienda usar el Sign-In de cliente automático como procedimiento recomendado. Para más información sobre cómo configurar los servidores DNS para el inicio de sesión automático de los clientes, consulte [requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) en la documentación referente a la planeación.

Si ya ha implementado el inicio de sesión automático de los clientes, consulte las siguientes secciones para configurarlo en sus directores.

<div>

## <a name="single-director-instance"></a>Instancia de director único

Si ya ha implementado el cliente Sign-In automático y apunta a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro SRV de DNS para que apunte al Director.

</div>

<div>

## <a name="director-pool"></a>Grupo de servidores de director

Si ya ha implementado el cliente Sign-In automático y está señalando a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro DNS SRV para que apunte al grupo de directores.

</div>

</div>

<span> </span>

</div>

</div>

</div>

