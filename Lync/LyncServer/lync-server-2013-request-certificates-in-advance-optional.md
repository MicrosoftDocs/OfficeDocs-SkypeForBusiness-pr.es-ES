---
title: 'Lync Server 2013: Solicitar los certificados con anterioridad (opcional)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6b376a2c1652dcaf255e39f6d112568b7c3bf31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Solicitar los certificados con anterioridad (opcional) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Los certificados son necesarios para todos los servidores internos que ejecutan Lync Server 2013, incluidos los servidores front-end Enterprise Edition, el servidor Standard Edition, el director, el servidor perimetral y el servidor de mediación independiente. Aunque se recomienda una entidad de certificación (CA) interna de empresa para los servidores internos, también puede usar una CA pública. Para obtener más información sobre los requisitos de certificado y sobre el uso de una CA pública, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.

La instalación de Lync Server 2013 incluye el Asistente para certificados, que facilita las tareas de solicitar, asignar e instalar certificados durante la implementación. Si desea solicitar certificados antes de instalar servidores (por ejemplo, para ahorrar tiempo durante la implementación real de servidores), puede hacerlo usando un equipo en el que estén instaladas las herramientas administrativas de Lync Server 2013 o mediante una solicitud de certificado procedimiento definido en la organización, siempre que se asegure de que los certificados son exportables y contienen todos los nombres alternativos de asunto necesarios. Solicitar certificados de antemano es opcional. Si no los solicita por adelantado, debe solicitarlos como parte de la configuración de cada servidor que requiera un certificado.

Esta documentación de implementación proporciona procedimientos para usar el Asistente para certificados con el fin de solicitar certificados como parte del proceso de configuración, según se describe en [configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para el Director de Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [Instale los archivos para mediar Server en lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) secciones de esta documentación de implementación. Si solicita certificados por adelantado, debe modificar los procedimientos de implementación de certificados en las secciones según corresponda para importar y asignar los certificados en lugar de solicitarlos en el momento de la implementación.

<div>


> [!NOTE]  
> Lync Server 2013 incluye compatibilidad con certificados SHA-256 para conexiones de clientes que ejecutan los sistemas operativos Windows&nbsp;vista, windows Server&nbsp;2008&nbsp;, Windows Server 2008 R2 y Windows 7, y Lync Phone Edition. Para admitir el acceso externo mediante SHA-256, un certificado externo es emitido por una entidad de certificación pública con SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

