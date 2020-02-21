---
title: 'Lync Server 2013: integración con Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489c5023ab995700762fa5e19ba361df1b49a6b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-09_

Exchange y Lync Server tienen un historial de integración y compatibilidad prolongado. Esta integración se hace patente sobre todo en sus respectivas aplicaciones cliente. Por ejemplo, se puede informar de la información de presencia de Lync en Microsoft Outlook; de forma similar, Lync puede usar el calendario de Outlook para actualizar automáticamente esa información de presencia. (Por ejemplo, Lync puede cambiar su estado a ocupado cada vez que el calendario muestre que tiene una reunión programada). Aunque no es necesario ejecutar Exchange para ejecutar Lync Server (o viceversa), hay muy poca duda de que usar los dos productos juntos epitomizes la definición del término "Better Together".

Esto es especialmente cierto con el lanzamiento de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013. Además de las características, como la mensajería unificada y la mensajería instantánea y la presencia, que se encuentran en Microsoft Exchange Server 2010 y Microsoft Lync Server 2010, las versiones 2013 de los productos de servidor incluyen varias funciones nuevas. Entre ellas, se incluyen las siguientes:

  - **Integración con el archivado de Lync**. En Lync Server 2013 los administradores siguen teniendo la opción de archivar las transcripciones de mensajería instantánea y de las conferencias web en SQL Server (de la misma manera que estas transcripciones se archivaron en Lync Server 2010). Sin embargo, de manera alternativa, los administradores pueden elegir que las transcripciones se archiven en Exchange 2013, almacenando dichas transcripciones en los buzones de usuario individuales de la misma forma en que Exchange archiva las comunicaciones. Esto significa que un único repositorio para todas las comunicaciones electrónicas (tanto de Exchange como de Lync Server) facilita en gran medida la búsqueda y recuperación de esas comunicaciones archivadas en caso de que surjan necesidades.

  - **Almacén de contactos unificado**. En Lync Server 2010, los usuarios tenían que mantener listas de contactos independientes en Outlook y Lync; de hecho, para asegurarse de que tenía los mismos contactos disponibles en ambos productos, tenía que mantener listas de contactos duplicadas, una para Outlook y otra para Lync. Sin embargo, con Lync Server 2013, los contactos de usuario se pueden almacenar en Exchange 2013 y en el almacén de contactos unificado. Usar un solo almacén de contactos permite a los usuarios mantener un solo conjunto de contactos, con el mismo conjunto de contactos disponible en Lync 2013, Outlook 2013 y Outlook Web Access 2013.

  - **Programación de reuniones de Lync desde OWA**. Con Lync Server 2013 y la integración de Exchange 2013, los usuarios pueden programar reuniones de Lync desde Outlook Web Access 2013.

  - **Fotografías de alta resolución**. Lync 2010 solo podría mostrar pequeñas fotos de sus contactos; Esto se debe a que esas fotos se almacenaron en Active Directory y Active Directory impone un límite de 48 píxeles por 48 píxeles en las fotos almacenadas. Sin embargo, con Lync Server 2013, las fotos se pueden almacenar en Microsoft Exchange; que permite fotos de alta resolución tan grandes como 648 píxeles por 648 píxeles. Como cabría esperar, se ha actualizado Lync 2013 para permitir que se muestren estas fotografías de alta resolución.

Tenga en cuenta que estas nuevas características requieren el uso de Lync Server 2013 y Exchange 2013. Además, los usuarios que esperan sacar el máximo partido de estas nuevas funciones deben tener cuentas en Lync Server 2013 y en Exchange 2013, y deben usar las versiones más recientes del software cliente (por ejemplo, Lync 2013). Por ejemplo, el almacén de contactos unificado no está disponible para los usuarios que se han hospedado en Lync Server 2010; del mismo modo, las fotos de alta resolución no se pueden mostrar en Lync 2010.

En esta documentación se proporciona información sobre la integración de Lync Server 2013 y Exchange 2013. incluye información paso a paso sobre cómo habilitar nuevas características, como la integración de archivado y el almacén de contactos unificado. Esta documentación no es una descripción de la instalación y la configuración inicial de estos dos productos. Para obtener más información sobre la implementación de Lync Server 2013, consulte el centro técnico [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)de lync Server 2013 en. Para obtener más información sobre la implementación de Exchange 2013, consulte el Exchange [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)2013 Tech Center en.

<div>

## <a name="in-this-section"></a>En esta sección

[Requisitos previos para integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configuración de aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificados](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configuración del uso de fotos de alta resolución en Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integración de Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

