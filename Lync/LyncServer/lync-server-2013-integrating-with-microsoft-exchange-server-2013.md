---
title: 'Lync Server 2013: Integración con Microsoft Exchange Server 2013'
TOCTitle: Integración de Lync Server 2013 y Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49889236
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Exchange y Lync Server cuentan con una larga historia en integración y compatibilidad. Esta integración se hace patente sobre todo en sus respectivas aplicaciones cliente. Por ejemplo, la información de presencia de Lync se puede notificar en Microsoft Outlook; del mismo modo, Lync puede usar el calendario de Outlook para actualizar automáticamente esa información de presencia. (Por ejemplo, Lync puede establecer su estado como Ocupado cuando el calendario muestra que tiene una reunión programada.) Aunque no es necesario ejecutar Exchange para ejecutar Lync Server (o viceversa), la complementación de ambos productos evidencia, sin duda, las ventajas del trabajo conjunto.

Esta afirmación cobra sentido especialmente con el lanzamiento de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013. Además de la mensajería unificada, la mensajería instantánea y la presencia, características que ya incluían Microsoft Exchange Server 2010 y Microsoft Lync Server 2010, las versiones de 2013 de los productos de servidor presentan una serie de características nuevas. Entre ellas, se incluyen las siguientes:

  - **Integración con el archivado de Lync** . En Lync Server 2013, los administradores siguen teniendo la opción de archivar transcripciones de conferencias web y de mensajería instantánea en SQL Server del mismo modo que en Lync Server 2010. La diferencia, no obstante, es que ahora los administradores podrán archivar dichas transcripciones en Exchange 2013, de manera que se almacenarán en los buzones de correo individuales de los usuarios de la misma manera en que Exchange archiva las comunicaciones. Con esto se consigue un único repositorio para todas las comunicaciones electrónicas (tanto de Exchange como de Lync Server), con lo que se facilita en gran medida la tarea de buscar y recuperar dichas comunicaciones en caso de que se necesiten.

  - **Almacén de contactos unificado** . En Lync Server 2010, los usuarios mantenían listas de contactos independientes en Outlook y en Lync; de hecho, para asegurarse de tener los mismos contactos en ambos productos, debían mantener listas de contactos duplicadas, una para Outlook y otra para Lync. Sin embargo, con Lync Server 2013, los contactos de los usuarios se pueden almacenar en Exchange 2013 y en el almacén de contactos unificado. El uso de un único almacén de contactos permite que los usuarios solo tengan que mantener un conjunto de contactos, que estará disponible en Lync 2013, Outlook 2013 y Outlook Web Access 2013.

  - **El programador de reuniones de Lync de OWA** . Con la integración de Lync Server 2013 y Exchange 2013, los usuarios pueden programar reunionres de Lync desde Outlook Web Access 2013.

  - **Fotografías de alta resolución** . Lync 2010 solo podía mostrar fotografías pequeñas de los contactos, ya que, como las fotos se almacenaban en Active Directory, su tamaño se limitaba a 48 por 48 píxeles. Con Lync Server 2013, no obstante, las fotografías se pueden almacenar en Microsoft Exchange, por lo que se pueden almacenar fotos de alta resolución y de un máximo de 648 por 648 píxeles. Con este cambio, Lync 2013 se ha actualizado para permitir la visualización de imágenes de alta resolución.

Tenga en cuenta que estas nuevas características requieren el uso de tanto Lync Server 2013 como Exchange 2013. Así mismo, los usuarios que deseen obtener todas las ventajas de estas características deberán tener cuentas de Lync Server 2013 y de Exchange 2013 y tendrán que usar las últimas versiones del software cliente (como Lync 2013). El almacén de contactos unificado, por ejemplo, no está disponible para los usuarios hospedados en Lync Server 2010; del mismo modo, no se pueden mostrar fotografías de alta resolución en Lync 2010.

En esta documentación encontrará información sobre la integración de Lync Server 2013 y Exchange 2013, además de instrucciones paso a paso para habilitar características nuevas como el almacén de contactos unificado y la integración con el archivado. Tenga en cuenta que en la documentación no se aborda la instalación y configuración inicial de estos productos. Para más información sobre la implementación de Lync Server 2013, visite el TechCenter de Lync Server 2013 en [http://go.microsoft.com/fwlink/?linkid=246127\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=246127%26clcid=0xc0a). Para más información sobre la implementación de Exchange 2013, visite el TechCenter de Exchange 2013 en [http://go.microsoft.com/fwlink/?linkid=268528\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268528%26clcid=0xc0a).

## En esta sección

[Requisitos previos para la integración de Microsoft Lync Server 2013 y Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configuración de aplicaciones de socio en Microsoft Lync Server 2013 y Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configuración de Microsoft Lync Server 2013 para utilizar el archivado de Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificado](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configuración del uso de fotografías de alta resolución en Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configuración de la mensajería unificada de Microsoft Exchange Server 2013 para el correo de voz de Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integrar Microsoft Lync Server 2013 y Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

