---
title: 'Lync Server 2013: configurar Lync Server 2013 para que funcione con la mensajería unificada en Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0dc8bc60f87b981a18f351df8ddd163d1b080be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Última modificación del tema:** 2013-04-03_

Para realizar este paso hace falta la utilidad de integración de Mensajería unificada de Exchange (OcsUmUtil.exe). Esta herramienta se encuentra en el servidor de Lync Server 2013 en el.. \\Archivos de\\programa archivos\\comunes carpeta de soporte\\de Microsoft Lync Server 2013.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Ejecución de la utilidad de integración de MU de Exchange

La utilidad de integración de Mensajería unificada de Exchange se debe ejecutar desde una cuenta de usuario con las siguientes características:

  - Pertenencia a los grupos RTCUniversalServerAdmins y RtcUniversalUserAdmins (que incluyen permisos para leer la configuración de Mensajería unificada de Exchange Server).

  - Derechos de usuario dentro del dominio para crear objetos de contacto en el contenedor de la unidad organizativa (OU) especificada.

Al ejecutar la utilidad de integración de Mensajería unificada de Exchange, se realizan las tareas siguientes:

  - Se crean objetos de contacto para cada número de operador automático y acceso de suscriptor que vayan a usar los usuarios de Enterprise Voice.

  - Comprueba que el nombre de cada plan de marcado de voz de empresa coincida con el contexto de teléfono correspondiente del plan de marcado de mensajería unificada (UM). Esta coincidencia solo es necesaria si el plan de marcado de mensajería unificada se ejecuta en una versión de Exchange *anterior* a Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Antes de ejecutar la utilidad de integración de mensajería unificada de Exchange, asegúrese de que ha hecho lo siguiente:
> <ul>
> <li><p>Cree uno o más planes de marcado de mensajería unificada de Exchange, como se describe en la documentación del producto de Exchange.</p>
> <p>Para Microsoft Exchange Server 2010, vea &quot;crear un plan&quot; de marcado de <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>mensajería unificada en.</p>
> <p>Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), vea &quot;cómo crear un plan&quot; de marcado de URI de SIP de <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>mensajería unificada en.</p></li>
> <li><p>Cree uno o varios planes de marcado de Lync Server correspondiente, tal y como se describe en <a href="lync-server-2013-create-a-dial-plan.md">Create a Dial plan in Lync Server 2013</a>.</p></li>
> <ul><li>Si usa una versión de Exchange anterior a Microsoft Exchange Server 2010 SP1, debe escribir el nombre de dominio completo (FQDN) del plan de marcado SIP de mensajería unificada de Exchange correspondiente en el campo <STRONG>nombre sencillo</STRONG> del plan de marcado de Lync Server 2013. Si usa Microsoft Exchange Server 2010 SP1 o el último Service Pack, esta coincidencia de nombres de plan de marcado no es necesaria.</li></ul>
> <li>Crear un operador automático y asegurarse de que tanto el número de acceso del suscriptor y el número del operador automático están en formato E.164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Para ejecutar la utilidad de integración de MU de Exchange

1.  En un servidor front-end, abra un símbolo del sistema y escriba **CD%\\CommonProgramFiles% soporte de\\Microsoft Lync Server 2013**y, a continuación, presione Entrar.

2.  Escriba **OcsUmUtil.exe** y pulse Entrar.

3.  Haga clic en **Cargar datos** para buscar todos los bosques de Exchange de confianza.

4.  En la lista **Planes de marcado de SIP**, seleccione un plan de marcado de SIP de MU para el que desee crear objetos de contacto y, a continuación, haga clic en **Agregar**.

5.  En el cuadro **Contacto**, acepte la unidad organizativa predeterminada o haga clic en **Examinar** para iniciar el **Selector de unidad organizativa**. En el cuadro **Selector de unidad organizativa**, puede seleccionar una unidad organizativa y hacer clic en **Aceptar**, o puede hacer clic en **Crear nueva unidad organizativa** para crear una nueva unidad organizativa en la raíz o en cualquier otra unidad organizativa del dominio (por ejemplo, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com") y, a continuación, hacer clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > El nombre distintivo (DN) de la unidad organizativa que ha seleccionado o creado se muestra ahora en el cuadro <STRONG>Unidad organizativa</STRONG>.

    
    </div>

6.  En el cuadro **Nombre**, acepte el nombre del plan de marcado predeterminado o escriba un nuevo nombre para mostrar para el objeto de contacto que está creando.
    
    <div>
    

    > [!NOTE]  
    > Por ejemplo, si va a crear un objeto de contacto de acceso de suscriptor, podría denominarlo simplemente Acceso de suscriptor.

    
    </div>

7.  En el cuadro **Dirección SIP**, acepte la dirección SIP predeterminada o escriba una nueva dirección SIP.
    
    <div>
    

    > [!NOTE]  
    > Si escribe una nueva dirección SIP, esta debe empezar por <STRONG>SIP:</STRONG> (es decir, "SIP:" incluidos los dos puntos).

    
    </div>

8.  En la lista **servidor o grupo** de servidores, seleccione el servidor Standard Edition o el grupo de servidores front-end en el que se va a habilitar el objeto de contacto.
    
    <div>
    

    > [!NOTE]  
    > Preferiblemente, el grupo de servidores que seleccione debe ser el mismo que el servidor en el que se han implementado los usuarios habilitados para Enterprise Voice y MU de Exchange.

    
    </div>

9.  En la lista **Número de teléfono**, seleccione **Escriba el número de teléfono** o **Use este número piloto de mensajería unificada de Exchange** y escriba un número de teléfono.

10. En la lista **Tipo de contacto**, seleccione el tipo de contacto que desea crear y, a continuación, haga clic en **Aceptar**.

11. Repita los pasos del 1 al 10 para los objetos de contacto adicionales que desee crear.
    
    <div>
    

    > [!NOTE]  
    > Debe crear al menos un contacto para cada operador automático. Si desea tener acceso externo, necesita también un contacto Acceso de suscriptor y especificar números DID (llamada directa a la extensión).

    
    </div>

</div>

Para comprobar que se han creado los objetos de contacto, abra Usuarios y equipos de Active Directory y seleccione la unidad organizativa en la que se crearon los objetos. Los objetos de contacto deben aparecer en el panel de detalles.

</div>

</div>

<span> </span>

</div>

</div>

</div>

