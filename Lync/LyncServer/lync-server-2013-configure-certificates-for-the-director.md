---
title: 'Lync Server 2013: Configurar los certificados para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurar los certificados para el director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Cuando ejecute el Asistente para certificados, asegúrese de haber iniciado sesión con una cuenta que sea miembro de un grupo al que se le hayan asignado los permisos adecuados para el tipo de plantilla de certificado que va a usar. De forma predeterminada, una solicitud de certificado de Lync Server 2013 usará la plantilla de certificado de servidor Web. Si usa una cuenta que sea miembro del grupo RTCUniversalServerAdmins para solicitar un certificado con esta plantilla, compruebe que el grupo tiene asignados los permisos de inscripción necesarios para usar esa plantilla.



</div>

Cada director requiere un certificado predeterminado, un certificado interno de la web y un certificado externo Web. Para obtener más información sobre los requisitos de certificados para directores, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación de planeación.

Use el siguiente procedimiento para configurar certificados de director. Repita el procedimiento para cada director. Los pasos de este procedimiento describen cómo configurar un certificado de una entidad de certificación (CA) raíz interna de empresa implementada por su organización y con procesamiento de solicitudes sin conexión. Para obtener más información sobre cómo obtener certificados de una entidad emisora externa, póngase en contacto con el equipo de soporte técnico.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Para configurar certificados para el grupo de directores o directores

1.  En el Asistente para la implementación de Lync Server, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.

2.  En la página **Asistente para certificados**, haga clic en **Solicitar**.

3.  En la página **solicitud de certificado** , haga clic en **siguiente**.

4.  En la página **peticiones demoradas o inmediatas** , acepte la opción predeterminada **enviar la solicitud inmediatamente a una entidad emisora de certificados en línea** y, a continuación, haga clic en **siguiente**.

5.  En la página **elegir una entidad emisora de certificados (CA)** , haga clic en la entidad emisora de certificados interna de Windows que desea usar y, después, haga clic en **siguiente**.

6.  En la página de la cuenta de la entidad emisora de **certificados** , especifique las credenciales alternativas que se usarán si la cuenta con la que inició sesión no tiene suficiente autoridad para solicitar el certificado y, a continuación, haga clic en **siguiente**.

7.  En la página **especificar plantilla de certificado alternativa** , haga clic en **siguiente**.

8.  En la página **nombre y configuración de seguridad** , puede especificar un **nombre descriptivo**, aceptar la 2048 y, a continuación, haga clic en **siguiente**.

9.  En la página información de la **organización** , especifique la información de la organización y, a continuación, haga clic en **siguiente**.

10. En la página **información geográfica** , especifique la información geográfica opcional y, a continuación, haga clic en **siguiente**.

11. En la página **nombre del asunto/nombres alternativos del asunto** , haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > La lista nombre alternativo del sujeto debe contener el nombre del equipo en el que está instalando el director (si es un único Director) o el nombre del grupo de directores, y los nombres simples de la dirección URL configurados para la organización.

    
    </div>

12. En la página **configuración del dominio SIP de los nombres alternativos de asunto (San)** , seleccione los **dominios SIP** configurados para todos los dominios que quiera que controle el director y, a continuación, haga clic en **siguiente**.

13. En la página **configurar nombres alternativos de asunto adicionales** , agregue los nombres alternativos de asunto adicionales necesarios y, a continuación, haga clic en **siguiente**.

14. En la página **Resumen de solicitud de certificado** , haga clic en **siguiente**.

15. En la página **comandos en ejecución** , haga clic en **siguiente** una vez que los comandos hayan terminado de ejecutarse.

16. En la página estado de la **solicitud de certificado en línea** , haga clic en **Finalizar**.

17. En la página **asignación de certificado** , haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si desea ver el certificado, haga doble clic en el certificado de la lista.

    
    </div>

18. En la página **Resumen de asignación de certificado** , haga clic en **siguiente**.

19. En la página **comandos en ejecución** , haga clic en **Finalizar** después de que los comandos hayan terminado de ejecutarse.

20. En la página **Asistente para certificados** , haga clic en **cerrar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

