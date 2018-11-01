---
title: 'Lync Server 2013: Habilitación de Office Web Apps Server y Lync Server 2013'
TOCTitle: Habilitación de Office Web Apps Server y Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48274875
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la integración de Office Web Apps Server y Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013 utiliza Servidor Office Web Apps para administrar las presentaciones de PowerPoint. Para obtener información sobre las ventajas de este enfoque, vea [Información general sobre la conferencia web en Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Para poder usar estas nuevas capacidades, los administradores deben instalar Servidor Office Web Apps y deben configurar Lync Server 2013 para que se comunique con Servidor Office Web Apps. Esta documentación proporciona información sobre cómo configurar Lync Server 2013 para que funcione con Servidor Office Web Apps. Esta documentación no proporciona información sobre cómo instalar Servidor Office Web Apps. Para ello, consulte el sitio web Implementar la infraestructura: Office Web Apps Server en [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0xc0a). Dicha guía incluye información completa sobre los requisitos de Servidor Office Web Apps. Tenga en cuenta que Servidor Office Web Apps debe estar instalado en un equipo individual que no ejecute Lync Server, Microsoft SQL Server ni cualquier otra aplicación de servidor. (No debe tener ninguna versión de Microsoft Office instalada en dicho equipo.) El equipo que se utilice para ejecutar Servidor Office Web Apps debe tener determinadas aplicaciones de software instaladas (entre las que se incluyen .NET Framework 4.5 y Windows PowerShell 3.0). Todos estos requisitos, así como la información sobre la configuración de certificados y Servicios de Internet Information Server (IIS), se describen con detalle en el sitio web Implementar la infraestructura: Office Web Apps Server en [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0xc0a).

Este documento trata los temas siguientes:

  - [Configuración de Lync Server 2013 para funcionar con Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Publicación de Office Web Apps Server con un servidor proxy inverso en Lync Server 2013](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Comprobación de la configuración de Office Web Apps Server en Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

