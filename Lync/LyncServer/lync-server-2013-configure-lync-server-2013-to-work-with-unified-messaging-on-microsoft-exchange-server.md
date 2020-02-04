---
title: 'Lync Server 2013: Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server'
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
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server

</div>

<div id="mainSection">

<div id="mainBody">

_**Última modificación del tema:** 2013-04-03_

Este paso requiere la utilidad de integración de mensajería unificada de Exchange (OcsUmUtil. exe). Esta herramienta se encuentra en el servidor de Lync Server 2013, en... \\Archivos\\comunes de programa\\archivos comunes carpeta de\\soporte técnico de Microsoft Lync Server 2013.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Ejecución de la utilidad de integración de MU de Exchange

La utilidad de integración de MU de Exchange debe ejecutarse desde una cuenta de usuario con las siguientes características:

  - Pertenencia a los grupos RTCUniversalServerAdmins y RtcUniversalUserAdmins (que incluye permisos para leer la configuración de mensajería unificada de Exchange Server).

  - Derechos de usuario dentro del dominio para crear objetos de contacto en el contenedor de unidades organizativas (OU) especificadas.

Al ejecutar la herramienta de integración de mensajería unificada de Exchange, se realizan las siguientes tareas:

  - Crea objetos de contacto para cada número de acceso de suscriptor y de operador automático que usarán los usuarios de voz de telefonía.

  - Comprueba que el nombre de cada plan de marcado de voz de empresa coincida con su contexto de teléfono del plan de marcado de mensajería unificada (UM) correspondiente. Esta coincidencia es necesaria solo si el plan de marcado de MU se está ejecutando en una versión de Exchange *anterior* a Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]
> Antes de ejecutar la utilidad de integración de MU de Exchange, asegúrese de que ha hecho lo siguiente:
> <ul>
> <li><p>Cree uno o varios planes de marcado de mensajería unificada de Exchange, como se describe en la documentación del producto de Exchange.</p>
> <p>Para Microsoft Exchange Server 2010, consulte &quot;crear un plan&quot; de marcado de <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>MU en.</p>
> <p>Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot;cómo crear un plan&quot; de marcado URI SIP Messaging Messaging en <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</p></li>
> <li><p>Cree uno o varios de los planes de marcado de Lync Server correspondientes, tal y como se describe en <a href="lync-server-2013-create-a-dial-plan.md">crear un plan de marcado en Lync Server 2013</a>.</p></li>
> <ul><li>Si está usando una versión de Exchange anterior a Microsoft Exchange Server 2010 SP1, debe escribir el nombre de dominio completo (FQDN) del plan de marcado SIP de mensajería unificada de Exchange (UM) correspondiente en el campo de <STRONG>nombre simple</STRONG> del plan de marcado de Lync Server 2013. Si está usando Microsoft Exchange Server 2010 SP1 o el Service Pack más reciente, la coincidencia de nombres de plan de marcado no es necesaria.</li></ul>
> <li>Cree un operador automático y asegúrese de que tanto el número de acceso del suscriptor como el número de operador automático estén en formato E. 164.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Para ejecutar la utilidad de integración de mensajería unificada de Exchange

1.  En un servidor front-end, abra un símbolo del sistema y escriba **CD%\\CommonProgramFiles% Microsoft Lync\\Server 2013 support**y, a continuación, presione Entrar.

2.  Escriba **OcsUmUtil. exe**y, a continuación, presione Entrar.

3.  Haga clic en **cargar datos** para buscar todos los bosques de confianza de Exchange.

4.  En la lista de los **planes de marcado SIP** , seleccione un plan de marcado SIP de mensajería unificada para el que desee crear objetos de contacto y, a continuación, haga clic en **Agregar**.

5.  En el cuadro **contacto** , acepte la unidad organizativa predeterminada o haga clic en **examinar** para iniciar el **selector de Uo**. En el cuadro **selector de ou** , seleccione una unidad organizativa y haga clic en **Aceptar**, o bien haga clic en **crear nueva** unidad organizativa para crear una nueva unidad organizativa bajo la raíz o cualquier otra unidad organizativa del dominio (por ejemplo, "ou = RTC Special Accounts, DC = fourthcoffee, DC = com") y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > El nombre distintivo (DN) de la OU que ha seleccionado o creado se muestra ahora en el cuadro <STRONG>unidad organizativa</STRONG> .

    
    </div>

6.  En el cuadro **nombre** , acepte el nombre del plan de marcado predeterminado o escriba un nuevo nombre para mostrar para el objeto de contacto que está creando.
    
    <div>
    

    > [!NOTE]  
    > Por ejemplo, si va a crear un objeto de contacto de acceso de suscriptor, es posible que simplemente le asigne el nombre de acceso de suscriptor.

    
    </div>

7.  En el cuadro **dirección SIP** , acepte la dirección SIP predeterminada o escriba una nueva.
    
    <div>
    

    > [!NOTE]  
    > Si escribe una dirección SIP nueva, debe comenzar con <STRONG>SIP:</STRONG> (es decir, "SIP:" incluyendo los dos puntos).

    
    </div>

8.  En la lista **servidor o grupo** de servidores, seleccione el servidor Standard Edition o el grupo de servidores front-end en el que se va a habilitar el objeto de contacto.
    
    <div>
    

    > [!NOTE]  
    > Preferiblemente, el grupo que seleccione es el mismo grupo en el que se implementan los usuarios habilitados para telefonía IP empresarial y mensajería unificada de Exchange.

    
    </div>

9.  En la lista **número de teléfono** , seleccione **Escriba el número de teléfono** o **use este número piloto de la mensajería unificada de Exchange** y, a continuación, escriba un número de teléfono.

10. En la lista **tipo de contacto** , seleccione el tipo de contacto que desea crear y, a continuación, haga clic en **Aceptar**.

11. Repita los pasos 1 a 10 para obtener objetos de contacto adicionales que desee crear.
    
    <div>
    

    > [!NOTE]  
    > Debes crear al menos un contacto para cada operador automático. Si desea obtener acceso externo, también necesitará un contacto de acceso de suscriptor y especificar números de marcado directo directo (sí).

    
    </div>

</div>

Para comprobar que los objetos de contacto se han creado, abra usuarios y equipos de Active Directory y seleccione la OU en la que se crearon los objetos. Los objetos de contacto deberían aparecer en el panel de detalles.

</div>

</div>

<span> </span>

</div>

</div>

</div>

