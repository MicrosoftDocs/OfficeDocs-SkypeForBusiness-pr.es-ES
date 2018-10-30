---
title: 'Lync Server 2013: Herramientas de administración de Windows PowerShell y Lync Server'
TOCTitle: Herramientas de administración de Windows PowerShell y Lync Server 2013
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59679369
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Herramientas de administración de Windows PowerShell y Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En Microsoft Lync Server 2013, las herramientas de administración se implementan utilizando Windows PowerShell. Windows PowerShell incluye un entorno de línea de comandos, comandos específicos del producto y un lenguaje de scripting completo. Entre las herramientas de Lync Server 2013 que se implementan con Windows PowerShell cabe citar las siguientes:

  - **Generador de topologías**. Generador de topologías se usa para crear, ajustar y publicar la topología planeada. Asimismo, valida la topología antes de empezar a realizar las instalaciones del servidor. Al instalar Lync Server 2013 en servidores individuales, estos leen la topología publicada como parte del proceso de instalación, y el programa de instalación implementa el servidor tal y como se haya indicado en la topología. Tras la instalación, se replica automáticamente la información de configuración a todos los servidores. Solo pueden agregarse componentes a la implementación utilizando el Generador de topologías.

  - **Shell de administración de Lync Server**. Puede utilizar Shell de administración de Lync Server como medio de administración integral de líneas de comandos en su implementación.

  - **Panel de control de Lync Server**. Puede utilizar la interfaz de usuario de Panel de control de Microsoft Lync Server 2013 para administrar las tareas más habituales de su implementación.

Estas herramientas utilizan cmdlets de Windows PowerShell para administrar su implementación, incluyendo cerca de 550 cmdlets específicos de un producto. Los cmdlets de seguridad incluidos en Lync Server 2013 se usan principalmente para administrar la autenticación, así como los permisos y derechos de los usuarios. Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del número de identificación personal (PIN). Asimismo, una serie de cmdlets permiten usar la nueva característica de control de acceso basado en roles (RBAC) para delegar el control administrativo de Lync Server 2013. Para obtener información detallada sobre los cmdlets de Lync Server, consulte [Shell de administración de Lync Server](lync-server-2013-lync-server-management-shell.md) en la documentación referente a las operaciones. Para obtener información detallada sobre el uso de Generador de topologías y Panel de control de Lync Server 2013 para administrar su implementación, consulte [Panel de control de Lync Server 2013](https://technet.microsoft.com/es-es/library/gg133224\(v=ocs.15\)) en la documentación referente a las operaciones.

Las características de seguridad de scripts de Windows PowerShell están diseñadas específicamente para ayudar a evitar algunos de los problemas de seguridad relacionados con scripts de tecnologías antiguas, incluyendo Microsoft Visual Basic Scripting Edition (VBScript). Las características de seguridad de Windows PowerShell están pensadas para crear un entorno en el que los usuarios no puedan ejecutar scripts fácilmente o sin saberlo. De forma predeterminada, las características de seguridad de Windows PowerShell están habilitadas. Puede modificar el estado de esas características para adaptarlo a sus necesidades de scripting y a una amplia variedad de objetivos de seguridad. Eso no significa que el shell impida a los usuarios ejecutar scripts. Lo que hace (de forma predeterminada) es que resulte difícil que los usuarios ejecuten scripts sin darse cuenta de que lo están haciendo. Para obtener información más detallada, vea Windows PowerShell Seguridad de scripts en [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).

