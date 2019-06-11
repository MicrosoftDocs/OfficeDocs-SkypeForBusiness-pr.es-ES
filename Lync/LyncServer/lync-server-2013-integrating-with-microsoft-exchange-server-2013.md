---
title: 'Lync Server 2013: integración con Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ba140e4f7e33684a280a9d9c4b71f1d7e141a65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-07-09_

Exchange y Lync Server tienen un largo historial de integración y compatibilidad. Esta integración es más apreciable dentro de la aplicación cliente correspondiente. Por ejemplo, se puede informar de la información de presencia de Lync en Microsoft Outlook. también puede usar el calendario de Outlook para actualizar automáticamente la información de presencia. (Por ejemplo, Lync puede cambiar su estado a ocupado siempre que su calendario muestre que tiene una reunión programada). Aunque no es necesario ejecutar Exchange para ejecutar Lync Server (o viceversa), hay pocas dudas acerca de que usar los dos productos juntos epitomizes la definición del término "mejor juntos".

Esto se aplica especialmente a la publicación de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013. Además de las características, como mensajería unificada y mensajería instantánea y presencia, que se encuentran en Microsoft Exchange Server 2010 y Microsoft Lync Server 2010, las versiones 2013 de los productos de servidor incluyen varias capacidades nuevas. Estas funciones incluyen elementos como los siguientes:

  - **Integración**de archivado de Lync. En Lync Server 2013, los administradores siguen teniendo la opción de archivar la mensajería instantánea y las transcripciones de conferencias por Internet en SQL Server (de la misma manera que estas transcripciones se archivaron en Lync Server 2010). Sin embargo, de forma alternativa, los administradores pueden optar por archivar transcripciones en Exchange 2013, almacenar dichas transcripciones en los buzones de los usuarios individuales de la misma forma en que Exchange archiva las comunicaciones. Eso significa que un único repositorio para todas sus comunicaciones electrónicas (tanto de Exchange como de Lync Server), lo que facilita la búsqueda y la recuperación de esas comunicaciones archivadas en caso de que surja la necesidad.

  - **Almacén de contactos unificado**. En Lync Server 2010, los usuarios tenían que mantener listas de contactos independientes en Outlook y Lync; de hecho, para asegurarse de que tenía los mismos contactos disponibles en los dos productos, tenía que mantener listas de contactos duplicadas, una para Outlook y otra para Lync. Sin embargo, con Lync Server 2013, los contactos de usuario se pueden almacenar en Exchange 2013 y en el almacenamiento de contactos unificado. Usar un único almacén de contactos permite a los usuarios mantener un solo conjunto de contactos, con el mismo conjunto de contactos disponibles en Lync 2013, Outlook 2013 y Outlook Web Access 2013.

  - **Programación de reuniones de Lync desde OWA**. Con la integración de Lync Server 2013 y Exchange 2013, los usuarios pueden programar reuniones de Lync desde Outlook Web Access 2013.

  - **Fotos de alta resolución**. Lync 2010 solo podría mostrar fotos pequeñas de sus contactos; Esto se debe a que esas fotos se almacenaron en Active Directory y Active Directory impone un píxel de 48 por 48 de tamaño de píxel en las fotos almacenadas. Sin embargo, con Lync Server 2013, las fotos se pueden almacenar en Microsoft Exchange. Esto permite que las fotos de alta resolución sean tan grandes como 648 píxeles por 648 píxeles. Como cabría esperar, Lync 2013 se ha actualizado para permitir la visualización de estas fotografías de alta resolución.

Tenga en cuenta que estas nuevas características requieren el uso de Lync Server 2013 y Exchange 2013. Además de eso, los usuarios que esperan sacar el máximo provecho de estas nuevas capacidades deben tener cuentas en Lync Server 2013 y en Exchange 2013, y deben usar las versiones más recientes del software cliente (por ejemplo, Lync 2013). Por ejemplo, el almacén de contactos unificado no está disponible para los usuarios que se han alojado en Lync Server 2010; del mismo modo, las fotos de alta resolución no se pueden mostrar en Lync 2010.

Esta documentación proporciona información acerca de la integración de Lync Server 2013 y de Exchange 2013. incluye información paso a paso sobre cómo habilitar nuevas características, como la integración de archivado y el almacenamiento de contactos unificado. Lo que no hace esta documentación es comentar la configuración inicial y la configuración de estos dos productos. Para obtener detalles sobre la implementación de Lync Server 2013, visite el centro tecnológico de [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)lync Server 2013 en. Para obtener más información sobre la implementación de Exchange 2013, visite el Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)2013 Tech Center en.

<div>

## <a name="in-this-section"></a>En esta sección

[Requisitos previos para integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configurar aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configuración de Microsoft Lync Server 2013 para usar el almacenamiento de contactos unificado](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configurar el uso de fotos de alta resolución en Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integración de Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

