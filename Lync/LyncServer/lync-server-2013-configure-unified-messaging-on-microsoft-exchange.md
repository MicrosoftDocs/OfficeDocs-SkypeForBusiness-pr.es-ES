---
title: 'Lync Server 2013: configurar la mensajería unificada en Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b39c10a3fb590acc99771663f5f6e23e3c3095e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520227"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-24_

En este tema se describe cómo configurar la mensajería unificada (MU) de Exchange en un servidor de Microsoft Exchange para su uso con telefonía IP empresarial.

<div>


> [!NOTE]  
> Los ejemplos de cmdlet de este tema proporcionan sintaxis para la versión Exchange 2007 del shell de administración de Exchange. Si está ejecutando Exchange 2010 o Exchange 2013, consulte la documentación correspondiente a la que se hace referencia.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Para configurar un servidor que ejecuta la mensajería unificada de Exchange Server

1.  Cree un plan de marcado del Identificador uniforme de recursos (URI) del Protocolo de inicio de sesión (SIP) para cada uno de sus perfiles de ubicación de Enterprise Voice. Si decide usar la Consola de administración de Exchange, cree un nuevo plan de marcado con la configuración de seguridad **Secured (preferiblemente)**.
    
    <div>
    

    > [!WARNING]  
    > Si establece el valor de configuración de seguridad en <STRONG>SIP Secured</STRONG> para requerir cifrado únicamente para el tráfico SIP, como se ha recomendado anteriormente, tenga en cuenta que esta configuración de seguridad del plan de marcado resulta insuficiente si el grupo de servidores front-end está configurado para requerir cifrado, lo que significa que el grupo de servidores requiere cifrado tanto para el tráfico SIP como para tráfico RTP. Si el plan de marcado y la configuración de seguridad del grupo no son compatibles, se producirá un error en todas las llamadas a la mensajería unificada de Exchange del grupo de servidores front-end, lo que indicará que hay una "configuración de seguridad incompatible".

    
    </div>
    
    Si utiliza el Shell de administración de Exchange, escriba:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Para obtener más información, consulte:
    
      - Para Office Communications Server 2007, consulte "cómo crear un plan de marcado de URI de SIP de mensajería unificada" en [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) y "New-UMDialplan: Exchange 2007 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .
    
      - Para Exchange 2010, consulte "crear un plan de marcado de mensajería unificada" en [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) y "New-UMDialplan: Exchange 2010 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .
    
      - Para Exchange 2013, consulte "mensajería unificada" en [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
    <div>
    

    > [!NOTE]  
    > El hecho de seleccionar un nivel de seguridad <STRONG>SIPSecured</STRONG> o <STRONG>Secured</STRONG> dependerá de si el Protocolo de transporte seguro en tiempo real (SRTP) está activado o desactivado para el cifrado de medios. Para la integración de Lync Server 2010 con mensajería unificada de Exchange, debe corresponderse con el nivel de cifrado en la configuración de medios de Lync Server. Para ver la configuración de medios de Lync Server, ejecute el cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Para obtener más información, consulte Get-CsMediaConfiguration en la documentación del shell de administración de Lync Server.<BR>Para obtener información detallada sobre cómo seleccionar la configuración de seguridad de VoIP adecuada, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">proceso de implementación para integrar la mensajería unificada local y Lync Server 2013</A>.

    
    </div>

2.  Ejecute el siguiente cmdlet para obtener el nombre de dominio completo (FQDN) de cada plan de marcado de Mensajería unificada:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .
    
      - Para Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .
    
      - Para Exchange 2013, consulte "mensajería unificada" en [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .

3.  Registre el nombre de plan de marcado de cada uno de los planes de marcado de Mensajería unificada. En función de la versión de Exchange Server, es posible que deba usar el FQDN de cada nombre de plan de marcado más adelante como nombre del plan de marcado de Lync Server correspondiente a cada plan de marcado de MU para que los nombres del plan de marcado sean coincidentes.
    
    <div>
    

    > [!NOTE]  
    > Los nombres del plan de marcado de Lync Server deben coincidir con los nombres de plan de marcado de mensajería unificada solo si el plan de marcado de MU se está ejecutando en una versión de Exchange <EM>anterior</EM> a Exchange 2010 SP1.

    
    </div>

4.  Agregue el plan de marcado al servidor que ejecuta la mensajería unificada de Exchange de la siguiente manera:
    
      - Si decide usar la Consola de administración de Exchange, puede agregar el plan de marcado desde la hoja de propiedades del servidor. Para obtener instrucciones específicas, consulte la documentación de producto de Exchange Server.
        
        Para Exchange 2007, consulte "cómo agregar un servidor de mensajería unificada a un plan de marcado" en [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .
        
        Para Exchange 2010, consulte "ver o configurar las propiedades de un servidor de mensajería unificada" en [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .
        
        Para Exchange 2013, consulte "mensajería unificada" en [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .
    
      - Si usa el Shell de administración de Exchange, ejecute lo siguiente para cada uno de los servidores de mensajería unificada de Exchange:
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Antes de realizar el siguiente paso, asegúrese de que todos los usuarios de Enterprise Voice se hayan configurado con un buzón de correo de Exchange Server.<BR>Para Exchange 2007, consulte la biblioteca de TechNet de Exchange Server 2007 en <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .<BR>Para Exchange 2010, consulte la biblioteca de TechNet de Exchange Server 2010 en <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .<BR>A la hora de especificar una directiva de buzón de correo para cada plan de marcado creado en el paso 1, seleccione la directiva predeterminada o una que haya creado.

    
    </div>

5.  Vaya a \<Exchange installation directory\> \\ scripts y, a continuación, si Exchange se implementa en un único bosque, escriba:
    ```console
    exchucutil.ps1
    ```
    Si Exchange se implementa en varios bosques, escriba:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    donde FQDN del bosque especifica el bosque en el que se implementa Lync Server.
    
    Si tiene uno o más planes de marcado de Mensajería unificada que estén asociados a varias puertas de enlace de IP, continúe en el paso 6. Si los planes de marcado están asociados a una única puerta de enlace de IP, omita el paso 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Asegúrese de reiniciar el servicio <STRONG>Front-end de Lync Server</STRONG> (rtcsrv.exe) <EM>después</EM> de ejecutar exchucutil.ps1. De lo contrario, Lync Server no detectará la mensajería unificada en la topología.

    
    </div>

6.  Utilizando el Shell de administración de Exchange o bien la Consola de administración de Exchange, deshabilite las llamadas realizadas de todas las puertas de enlace IP asociadas a cada uno de los planes de marcado, excepto de una.
    
    <div>
    

    > [!NOTE]  
    > Este paso es necesario para asegurarse de que las llamadas salientes realizadas por el servidor que ejecuta la mensajería unificada de Exchange Server a los usuarios externos (por ejemplo, como en el caso de los escenarios de reproducción en teléfono) atraviesen de forma confiable el Firewall corporativo.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Cuando seleccione la puerta de enlace IP de mensajería unificada a través de la cual van a pasar las llamadas realizadas, elija la que probablemente vaya a administrar la mayor parte del tráfico. No permita el tráfico saliente a través de una puerta de enlace IP que se conecte a un grupo de directores de Lync Server. Evite también los grupos de servidores en otro sitio central o sucursal. Puede usar alguno de los métodos siguientes para impedir que las llamadas realizadas pasen por una puerta de enlace IP:

    
    </div>
    
      - Si utiliza el Shell de administración de Exchange, deshabilite cada puerta de enlace de IP ejecutando el comando siguiente:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Para Exchange 2007, consulte "Set-UMIPGateway: ayuda de Exchange 2007" en [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .
        
        Para Exchange 2010, consulte "Set-UMIPGateway: ayuda de Exchange 2010" en [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .
    
      - Si utiliza la Consola de administración de Exchange, desactive la casilla **Permitir llamadas realizadas a través de esta puerta de enlace IP de MU**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si su plan de marcado del URI del SIP de Mensajería unificada está asociado a una única puerta de enlace IP, no impida que las llamadas realizadas pasen a través de esta puerta de enlace.

    
    </div>

7.  Cree un operador automático de mensajería unificada para cada plan de marcado de Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > No incluya espacios en el nombre del operador automático.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .
    
      - Para Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .
    
    El siguiente paso debe realizarse para cada usuario después de haber habilitado a los usuarios de Lync Server para la telefonía IP empresarial y conocer sus URI de SIP.

8.  Asocie los usuarios de Mensajería unificada de Exchange (cada uno de los cuales debe haberse configurado con un buzón de correo de Exchange) al plan de marcado de Mensajería unificada y cree un URI de SIP para cada usuario.
    
    <div>
    

    > [!NOTE]  
    > El <STRONG>SIPResourceIdentifier</STRONG> del siguiente ejemplo debe ser la dirección SIP del usuario de Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Para más información, vea:
    
      - Para Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .
    
      - Para Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" en [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

