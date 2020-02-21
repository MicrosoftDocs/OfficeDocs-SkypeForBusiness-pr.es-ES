---
title: 'Lync Server 2013: configurar certificados para el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5fef23ca24d9a09d326b75ec2ad2e30704852f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurar certificados para el Director en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Al ejecutar el Asistente para certificados, asegúrese de que ha iniciado sesión usando una cuenta que es miembro de un grupo con los permisos asignados adecuados para el tipo de plantilla de certificado que use. De forma predeterminada, una solicitud de certificado 2013 de Lync Server usará la plantilla de certificado del servidor Web. Si usa una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado usando esta plantilla, compruebe que el grupo tenga asignados los permisos Inscribir necesarios para usar la plantilla.



</div>

Cada director necesita un certificado predeterminado, así como certificado web interno y otro externo. Para obtener más información sobre los requisitos de certificados para directores, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) en la documentación referente a la planeación.

Use el siguiente procedimiento para configurar certificados de director (repítalo con cada uno de los directores). Los pasos de este procedimiento detallan cómo se configura un certificado procedente de una entidad de certificación raíz de empresa interna implementada por la organización y con procesamiento de una solicitud sin conexión. Para obtener información detallada sobre cómo obtener certificados de una CA externa, póngase en contacto con el equipo de atención al cliente.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Para configurar certificados para el director o grupo de directores

1.  En el Asistente para la implementación de Lync Server, junto a **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.

2.  En la página **Asistente para certificados**, haga clic en **Solicitud**.

3.  En la página **Solicitud de certificado**, haga clic en **Siguiente**.

4.  En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente** y haga clic en **Siguiente**.

5.  En la página **Elegir una entidad de certificación**, haga clic en la entidad de certificación de Windows interna que desee usar y haga clic en **Siguiente**.

6.  En la página **Cuenta de entidad de certificación**, especifique las credenciales que se van a usar de forma alternativa en caso de que la cuenta con la que se ha iniciado sesión no tenga suficiente autoridad para solicitar el certificado. A continuación, haga clic en **Siguiente**.

7.  En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente**.

8.  En la página **Nombre y configuración de seguridad**, puede indicar un **Nombre descriptivo**, aceptar la longitud de clave de 2048 bits y hacer clic en **Siguiente**.

9.  En la página **Información de la organización**, aporte información sobre la organización si lo desea y, a continuación, haga clic en **Siguiente**.

10. En la página **Información geográfica**, aporte información geográfica si lo desea y, a continuación, haga clic en **Siguiente**.

11. En la página **Nombre del sujeto o nombres alternativos del sujeto**, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > En la lista de nombres alternativos del sujeto debe figurar el nombre del equipo en el que se va a instalar el director (si se trata de uno solo) o el nombre del grupo de directores, así como los nombres de las direcciones URL sencillas configuradas para la organización.

    
    </div>

12. En la página **Configuración de dominio SIP**, seleccione **Dominios SIP configurados** para todos los dominios que quiera que el director controle y, a continuación, haga clic en **Siguiente**.

13. En la página **Configurar nombres de sujeto alternativos adicionales**, agregue los nombres de sujeto alternativos adicionales que desee y haga clic en **Siguiente**.

14. En la página **Resumen de la solicitud de certificados**, haga clic en **Siguiente**.

15. En la página **Ejecución de comandos**, haga clic en **Siguiente** cuando los comandos hayan terminado de ejecutarse.

16. En la página **Estado de solicitud del certificado en línea**, haga clic en **Finalizar**.

17. En la página **Asignación de certificados**, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si desea ver el certificado, haga doble clic en él en la lista.

    
    </div>

18. En la página **Resumen de asignación de certificados**, haga clic en **Siguiente**.

19. En la página **Ejecución de comandos**, haga clic en **Finalizar** cuando los comandos hayan terminado de ejecutarse.

20. En la página **Asistente para certificados**, haga clic en **Cerrar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

