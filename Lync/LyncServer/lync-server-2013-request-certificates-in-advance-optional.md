---
title: 'Lync Server 2013: solicitar certificados de antemano (opcional)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691efbbc1adad91ce63cfa0bca5fba6f11b5aea2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Solicitar certificados de antemano (opcional) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Los certificados son necesarios para todos los servidores internos que ejecutan Lync Server 2013, incluidos cada servidor front-end Enterprise Edition, un servidor Standard Edition, un director, un servidor perimetral y un servidor de mediación independiente. Aunque para los servidores internos se recomienda una entidad de certificación (CA) empresarial interna, también puede usar una pública. Para obtener más información sobre los requisitos de certificado y el uso de una entidad de certificación pública, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación referente a la planeación.

El programa de instalación de Lync Server 2013 incluye el Asistente para certificados, que facilita las tareas de solicitar, asignar e instalar certificados durante la implementación. Si desea solicitar certificados antes de instalar servidores (por ejemplo, para ahorrar tiempo durante la implementación real de servidores), puede hacerlo con un equipo en el que estén instaladas las herramientas administrativas de Lync Server 2013 o mediante una solicitud de certificado. procedimiento definido en la organización, siempre que se asegure de que los certificados son exportables y contienen todos los nombres alternativos de sujeto necesarios. Solicitar certificados por adelantado es opcional. Si no los solicita por adelantado, debe solicitarlos como parte de la configuración de cada servidor que requiera un certificado.

Esta documentación sobre la implementación proporciona procedimientos para usar el Asistente para certificados para solicitar certificados como parte del proceso de instalación, como se describe en [configurar certificados para servidores en Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para el Director en Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [instalar los archivos para el servidor de mediación en las secciones de Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de esta documentación de implementación. Si solicita certificados por adelantado, deberá modificar los procedimientos de implementación de certificados en estas secciones según convenga para importar y asignar los certificados, en lugar de solicitarlos durante la implementación.

<div>


> [!NOTE]  
> Lync Server 2013 incluye compatibilidad con certificados SHA-256 para conexiones de clientes que ejecutan los sistemas operativos Windows&nbsp;vista, windows Server&nbsp;2008&nbsp;, Windows Server 2008 R2 y Windows 7, y Lync Phone Edition. Para permitir el acceso externo mediante SHA-256, el certificado externo lo emite una CA pública que usa SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

