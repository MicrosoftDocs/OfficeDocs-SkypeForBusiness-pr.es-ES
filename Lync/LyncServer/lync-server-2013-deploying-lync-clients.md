---
title: Implementación de clientes de Lync en Lync Server 2013
TOCTitle: Implementación de clientes de Lync en Lync Server 2013
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48275006
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de clientes de Lync en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

Lync 2013 introduce un enfoque distinto de la implementación del cliente. Apartándose de las versiones anteriores, Lync 2013 ya no tiene su propio instalador. En cambio, Lync se incluye en el programa de instalación de Office 2013. Para implementar Lync 2013 con sus usuarios, puede utilizar las herramientas de personalización y los métodos de instalación de Office 2013.

  - **Office 2013 Windows Installer** es un paquete de instalación basado en Windows Installer que consiste en varios archivos MSI. Un paquete MSI central de lenguaje neutral se combina con uno o más paquetes de lenguaje específico para hacer un producto completo. La instalación junta los paquetes individuales y realiza tareas de mantenimiento y personalización durante y tras finalizar la instalación de Office en los equipos de los usuarios. Los temas de esta sección describen cómo utilizar y personalizar el Windows Installer Office 2013 para implementar Lync 2013.

  - **Office 2013 Click-to-Run** es un programa de instalación que transmite los archivos de instalación de Office al usuario del portal de Microsoft Office 365. Los administradores pueden personalizar la instalación utilizando la herramienta de implementación de Office para Click-to-Run. Puesto que Click-to-Run de Office 2013 se utiliza principalmente en el entorno Microsoft Office 365, este método de instalación no se describe en detalle en esta sección. Hay información detallada sobre el uso y la personalización de la instalación de Click-to-Run en la documentación del Kit de recursos de Office 2013. Los administradores también pueden descargar el programa Click-to-Run de Office 2013 y los archivos de origen de lenguaje a una ubicación local, lo cual es útil cuando quiere minimizar la demanda en la red o evitar que los usuarios instalen el software desde Internet debido a los requisitos de seguridad corporativos.

Los temas de esta sección se centran en cómo implementar clientes utilizando el instalador basado en MSI de Office 2013. Su referencia principal debe ser la documentación del Kit de recursos de Office 2013, que describe en detalle cómo preparar su infraestructura, personalizar la instalación e implementar Office 2013. Sin embargo, debe utilizarla documentación de Office junto con los temas de esta sección, que señalan consideraciones de implementación que son específicas de Lync 2013.


> [!NOTE]
> <UL>
> <LI>
> <P>El Complemento para conferencia en línea para Lync 2013, que admite la administración de la reunión desde dentro del cliente de colaboración y mensajería de Outlook, se instala automáticamente con Lync 2013.</P>
> <LI>
> <P>El programa de instalación de Office 2013 no desinstala versiones previas de Lync u Office Communicator. El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</P></LI></UL>



## En esta sección

  - [Personalización de la instalación de clientes](lync-server-2013-customizing-client-installation.md)

  - [Personalización del comportamiento de Lync y de la interfaz de usuario](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Personalización del complemento para reunión en línea en Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Configuración de la página de participación en reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Configuración de versiones de cliente admitidas](lync-server-2013-configuring-supported-client-versions.md)

  - [Configurar el modo de privacidad de presencia mejorada](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

