---
title: 'Lync Server 2013: configuración de mensajería unificada en Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcbdbfbca5f532b1ca192cc0e9d89e93e3c8acb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

En este tema se describe cómo configurar la mensajería unificada de Exchange en un servidor de Microsoft Exchange para su uso con telefonía IP empresarial.

<div>


> [!NOTE]  
> Los ejemplos de cmdlet de este tema proporcionan la sintaxis de la versión de Exchange 2007 del shell de administración de Exchange. Si está ejecutando Exchange 2010 o Exchange 2013, consulte la documentación correspondiente a la que se hace referencia.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Para configurar un servidor que ejecute mensajería unificada de Exchange Server

1.  Crear un plan de marcado identificador uniforme de recursos (URI) de protocolo de inicio de sesión (SIP) de UM para cada uno de los perfiles de ubicación de telefonía IP empresarial. Si elige usar la consola de administración de Exchange, cree un nuevo plan de marcado con la configuración de seguridad **segura (preferida)**.
    
    <div>
    

    > [!WARNING]  
    > Si establece el valor de configuración de seguridad en <STRONG>SIP protegido</STRONG> para requerir el cifrado solo para el tráfico SIP, como se recomienda anteriormente, tenga en cuenta que esta configuración de seguridad en un plan de marcado es insuficiente si el grupo de servidores Front-End está configurado para requerir cifrado, lo que significa el grupo requiere cifrado para el tráfico de SIP y de RTP. Cuando el plan de marcado y la configuración de seguridad del grupo no son compatibles, todas las llamadas a la mensajería unificada de Exchange desde el grupo de servidores front-end producirán un error que indica que tiene una "configuración de seguridad incompatible".

    
    </div>
    
    Si usa el shell de administración de Exchange, escriba:
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    Para obtener más información, consulte:
    
      - Para Office Communications Server 2007, consulte "cómo crear un plan de marcado URI del SIP de mensajería unificada" en [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) y "New-UMDialplan: Exchange 2007 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)Help" en.
    
      - Para Exchange 2010, consulte "crear un plan de marcado de MU [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) " en y "New-UMDialplan: Exchange 2010 Help [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)" en.
    
      - Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.
    
    <div>
    

    > [!NOTE]  
    > Si selecciona un nivel de seguridad de <STRONG>SIPSecured</STRONG> o <STRONG>Secure</STRONG> , dependerá de si el protocolo de transporte seguro en tiempo real (SRTP) está activado o desactivado para el cifrado de multimedia. Para la integración de Lync Server 2010 con la mensajería unificada de Exchange, debe coincidir con el nivel de cifrado en la configuración de multimedia de Lync Server. Para ver la configuración de multimedia de Lync Server, ejecute el cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Para obtener más información, vea Get-CsMediaConfiguration en la documentación del shell de administración de Lync Server.<BR>Para más información sobre cómo seleccionar la configuración de seguridad de VoIP adecuada, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">proceso de implementación para la integración de mensajería unificada local y Lync Server 2013</A>.

    
    </div>

2.  Ejecute el siguiente cmdlet para obtener el nombre de dominio completo (FQDN) de cada plan de marcado de MU:
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).
    
      - Para Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).
    
      - Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.

3.  Grabe el nombre del plan de marcado de cada plan de marcado de MU. Dependiendo de su versión de Exchange Server, es posible que tenga que usar el FQDN de cada nombre de plan de marcado más tarde como el nombre de cada plan de marcado de mensajería unificada de Lync Server correspondiente para que coincidan los nombres del plan de marcado.
    
    <div>
    

    > [!NOTE]  
    > Los nombres de los planes de marcado de Lync Server deben coincidir con los nombres de plan de marcado de MU solo si el plan de marcado de MU se está ejecutando en una versión de Exchange <EM>anterior</EM> a Exchange 2010 SP1.

    
    </div>

4.  Agregue el plan de marcado al servidor que ejecuta la mensajería unificada de Exchange de la siguiente manera:
    
      - Si decide usar la consola de administración de Exchange, puede Agregar el plan de marcado desde la hoja de propiedades del servidor. Para obtener instrucciones específicas, consulte la documentación del producto Exchange Server.
        
        Para Exchange 2007, consulte "cómo agregar un servidor de mensajería unificada a un plan de [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)marcado" en.
        
        Para Exchange 2010, consulte "ver o configurar las propiedades de un servidor de mensajería unificada" en [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).
        
        Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.
    
      - Si usa el shell de administración de Exchange, ejecute lo siguiente para cada uno de los servidores de mensajería unificada de Exchange:
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umservice -instance $ums[0]
    
    <div>
    

    > [!NOTE]  
    > Antes de realizar el siguiente paso, asegúrese de que todos los usuarios de Enterprise Voice se han configurado con un buzón de Exchange Server.<BR>Para Exchange 2007, consulte la biblioteca de TechNet de Exchange Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>2007 en.<BR>Para Exchange 2010, consulte la biblioteca de TechNet de Exchange Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>2010 en.<BR>Cuando especifique una directiva de buzón para cada plan de marcado que creó en el paso 1, seleccione la directiva predeterminada o la que ha creado.

    
    </div>

5.  Vaya a \<las secuencias de\>\\comandos del directorio de instalación de Exchange y, si Exchange se implementa en un único bosque, escriba:
    
        exchucutil.ps1
    
    O bien, si Exchange se implementa en varios bosques, escriba:
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    donde FQDN de bosque especifica el bosque en el que se implementa Lync Server.
    
    Si tiene uno o varios planes de marcado de MU asociados con varias puertas de enlace IP, continúe con el paso 6. Si los planes de marcado están asociados a una sola puerta de enlace IP, omita el paso 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Asegúrese de reiniciar el servicio <STRONG>front-end de Lync Server</STRONG> (RtcSrv. exe) <EM>después</EM> de ejecutar ExchUCUtil. ps1. De lo contrario, Lync Server no detectará la mensajería unificada en la topología.

    
    </div>

6.  Con el shell de administración de Exchange o la consola de administración de Exchange, deshabilite las llamadas salientes para todas las puertas de enlace IP asociadas a cada uno de los planes de marcado, excepto una.
    
    <div>
    

    > [!NOTE]  
    > Este paso es necesario para asegurarse de que las llamadas salientes realizadas por el servidor que ejecuta la mensajería unificada de Exchange Server a usuarios externos (por ejemplo, como sucede con los escenarios de reproducción en teléfono) atraviesen el Firewall de la empresa de manera confiable.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Al seleccionar la puerta de enlace IP de MU a través de la cual permitir llamadas salientes, elige la que es probable que gestione la mayor parte del tráfico. No permita el tráfico saliente a través de una puerta de enlace IP que se conecte a un grupo de directores de Lync Server. Además, evite grupos en otro sitio central o en un sitio de sucursal. Puede usar cualquiera de los métodos siguientes para bloquear las llamadas salientes para que no pasen por una puerta de enlace IP:

    
    </div>
    
      - Si usa el shell de administración de Exchange, deshabilite cada puerta de enlace IP ejecutando el siguiente comando:
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Para Exchange 2007, consulte "Set-UMIPGateway: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).
        
        Para Exchange 2010, consulte "Set-UMIPGateway: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).
    
      - Si usa la consola de administración de Exchange, desactive la casilla **permitir llamadas salientes a través de esta puerta de enlace IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Si el plan de marcado de URI del SIP de MU está asociado con una sola puerta de enlace IP, no devuelva las llamadas salientes a través de esta puerta de enlace.

    
    </div>

7.  Crear un operador automático de mensajería unificada para cada plan de marcado de Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > No incluya espacios en el nombre del operador automático.

    
    </div>
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).
    
      - Para Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).
    
    El paso siguiente debe realizarse para cada usuario después de haber habilitado a los usuarios de Lync Server para Enterprise Voice y conocer sus URI de SIP.

8.  Asocie los usuarios de mensajería unificada de Exchange (cada uno de los cuales se debe configurar con un buzón de correo de Exchange) con el plan de marcado de MU y cree un URI de SIP para cada usuario.
    
    <div>
    

    > [!NOTE]  
    > El <STRONG>SIPResourceIdentifier</STRONG> de la siguiente muestra debe ser la dirección SIP del usuario de Lync Server.

    
    </div>
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)en.
    
      - Para Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

