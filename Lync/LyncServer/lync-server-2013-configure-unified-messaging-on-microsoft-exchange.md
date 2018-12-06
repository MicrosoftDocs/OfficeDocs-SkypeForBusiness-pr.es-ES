---
title: Configuración de la mensajería unificada de Microsoft Exchange en Lync Server 2013
TOCTitle: Configuración de la mensajería unificada de Microsoft Exchange en Lync Server 2013
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48274329
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la mensajería unificada de Microsoft Exchange en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describe cómo configurar la Mensajería unificada de Exchange (UM) en un Microsoft Exchange Server para usarla con Telefonía IP empresarial.


> [!NOTE]
> Los ejemplos de cmdlet de este tema proporcionan la sintaxis para la versión Exchange 2007 del shell de administración de Exchange. Si está ejecutando Exchange 2010 o Exchange 2013, consulte la documentación correspondiente según se indica.



## Para configurar un servidor que ejecuta la mensajería unificada de Exchange Server

1.  Cree un plan de marcado del Identificador uniforme de recursos (URI) del Protocolo de inicio de sesión (SIP) para cada uno de sus perfiles de ubicación de Telefonía IP empresarial. Si decide usar la Consola de administración de Exchange, cree un nuevo plan de marcado con la configuración de seguridad **Secured (preferiblemente)**.
    
    > [!WARNING]  
    > Si establece el valor de configuración de seguridad en <strong>SIP Secured</strong> para requerir cifrado únicamente para el tráfico SIP, como se ha recomendado anteriormente, tenga en cuenta que esta configuración de seguridad del plan de marcado resulta insuficiente si el grupo de servidores front-end está configurado para requerir cifrado, lo que significa que el grupo de servidores requiere cifrado tanto para el tráfico SIP como para tráfico RTP. Cuando la configuración del plan de marcado no es compatible con la configuración de seguridad del grupo de servidores, todas las llamadas a Mensajería unificada de Exchange desde el grupo de servidores front-end devolverán un error que le informará de que tiene una “Configuración de seguridad incompatible”.
    
    
    Si utiliza el Shell de administración de Exchange, escriba:
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    Para obtener más información, consulte:
    
      - Para Office Communications Server 2007, consulte "Cómo crear un plan de marcado del URI del SIP de mensajería unificada" en [http://go.microsoft.com/fwlink/?linkid=268632\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268632%26clcid=0xc0a) y "New-UMDialplan: Ayuda de Exchange 2007", en [http://go.microsoft.com/fwlink/?linkid=268666\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268666%26clcid=0xc0a).
    
      - Para Exchange 2010, consulte "Crear un plan de marcado de MU" en [http://go.microsoft.com/fwlink/?linkid=268674\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268674%26clcid=0xc0a) y "New-UMDialplan: Ayuda de Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=268680\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268680%26clcid=0xc0a).
    
      - Para Exchange 2013, vea la sección "Mensajería unificada" en [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a).
    

    > [!NOTE]
    > El hecho de seleccionar un nivel de seguridad <STRONG>SIPSecured</STRONG> o <STRONG>Secured</STRONG> dependerá de si el Protocolo de transporte seguro en tiempo real (SRTP) está activado o desactivado para el cifrado de medios. En el caso de la integración de Lync Server 2010 con la mensajería unificada de Exchange, esto deberá corresponderse con el nivel de cifrado de la configuración de medios de Lync Server. La Lync Server configuración de medios puede visualizarse ejecutando el cmdlet <STRONG>Get-CsMediaConfiguration</STRONG>. Para obtener más información, consulte Get-CsMediaConfiguration en la documentación del Shell de administración de Lync Server.<BR>Para obtener información detallada sobre la selección de la configuración de seguridad de VoIP adecuada, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013</A>.



2.  Ejecute el siguiente cmdlet para obtener el nombre de dominio completo (FQDN) de cada plan de marcado de Mensajería unificada:
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "Get-UMDialplan: Ayuda de Exchange 2007" en [http://go.microsoft.com/fwlink/?linkid=268678\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268678%26clcid=0xc0a).
    
      - Para Exchange 2010, consulte "Get-UMDialplan: Ayuda de Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=268679\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268679%26clcid=0xc0a).
    
      - Para Exchange 2013, vea la sección "Mensajería unificada" en [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a).

3.  Registre el nombre de plan de marcado de cada uno de los planes de marcado de Mensajería unificada. En función de su versión de Exchange Server, es posible que, para que los nombres de plan de marcado coincidan, después deba usar el FQDN de cada uno de los nombres de plan de marcado como el nombre de plan de marcado Lync Server correspondiente al plan de marcado de MU.
    

    > [!NOTE]
    > Los nombres de plan de marcado de Lync Server deben coincidir con los nombres de plan de marcado de mensajería instantánea únicamente si el plan de marcado de mensajería instantánea se está ejecutando en una versión de Exchange <EM>anterior</EM> a Exchange 2010 SP1.



4.  Agregue el plan de marcado al servidor que ejecuta Mensajería unificada de Exchange del siguiente modo:
    
      - Si decide usar la Consola de administración de Exchange, puede agregar el plan de marcado desde la hoja de propiedades del servidor. Para obtener instrucciones específicas, consulte la documentación de producto de Exchange Server.
        
        Para Exchange 2007, consulte "Cómo agregar un servidor de mensajería unificada a un plan de marcado", en [http://go.microsoft.com/fwlink/?linkid=268681\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268681%26clcid=0xc0a).
        
        Para Exchange 2010, consulte "Ver o configurar las propiedades de un servidor de mensajería unificada" en [http://go.microsoft.com/fwlink/?linkid=268682\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268682%26clcid=0xc0a).
        
        Para Exchange 2013, vea la sección "Mensajería unificada" en [http://go.microsoft.com/fwlink/?linkid=266579\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=266579%26clcid=0xc0a).
    
      - Si usa el Shell de administración de Exchange, ejecute lo siguiente para cada uno de los servidores de mensajería unificada de Exchange:
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umserver -instance $ums[0]
    

    > [!NOTE]
    > Antes de realizar el siguiente paso, asegúrese de que todos los usuarios de Enterprise Voice se hayan configurado con un buzón de correo de Exchange Server.<BR>Para Exchange 2007, consulte la biblioteca de TechNet de Exchange Server 2007 en <A href="http://go.microsoft.com/fwlink/?linkid=268685%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268685&amp;clcid=0xC0A</A>.<BR>Para Exchange 2010, consulte la biblioteca de Technet de Exchange Server 2010 en <A href="http://go.microsoft.com/fwlink/?linkid=268686%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268686&amp;clcid=0xC0A</A>.<BR>A la hora de especificar una directiva de buzón de correo para cada plan de marcado creado en el paso 1, seleccione la directiva predeterminada o una que haya creado.



5.  Desplácese hasta el \<*Exchange installation directory*\>\\Scripts y, a continuación, en el caso de que Exchange se haya implementado en un bosque único, escriba lo siguiente:
    
        exchucutil.ps1
    
    En el caso de que Exchange se haya implementado en varios bosques, escriba lo siguiente:
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    donde *FQDN del bosque* especifica el bosque en el que se ha implementado Lync Server.
    
    Si tiene uno o más planes de marcado de Mensajería unificada que estén asociados a varias puertas de enlace de IP, continúe en el paso 6. Si los planes de marcado están asociados a una única puerta de enlace de IP, omita el paso 6.
    
    > [!IMPORTANT]  
    > Asegúrese de reiniciar el servicio <strong>Lync Server Front-End</strong> (rtcsrv.exe) <em>después</em> de ejecutar exchucutil.ps1. De lo contrario, Lync Server no detectará la Mensajería unificada en la topología.
    


6.  Utilizando el Shell de administración de Exchange o bien la Consola de administración de Exchange, deshabilite las llamadas realizadas de todas las puertas de enlace IP asociadas a cada uno de los planes de marcado, excepto de una.
    

    > [!NOTE]
    > Este paso es necesario para asegurarse de que las llamadas realizadas efectuadas por el servidor que ejecuta la Mensajería unificada de Exchange Server a los usuarios externos (por ejemplo, en el caso de escenarios de reproducción en teléfono) pasen de forma segura por el firewall corporativo.

    
    > [!IMPORTANT]  
    > Cuando seleccione la puerta de enlace IP de mensajería unificada a través de la cual van a pasar las llamadas realizadas, elija la que probablemente vaya a administrar la mayor parte del tráfico. No permita el tráfico de salida a través de una puerta de enlace IP que se conecte a un grupo de servidores de directores de Lync Server. Evite también los grupos de servidores en otro sitio central o sucursal. Puede usar alguno de los métodos siguientes para impedir que las llamadas realizadas pasen por una puerta de enlace IP:
    
    
      - Si utiliza el Shell de administración de Exchange, deshabilite cada puerta de enlace de IP ejecutando el comando siguiente:
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        Para Exchange 2007, consulte "Set-UMIPGateway: Ayuda de Exchange 2007" en [http://go.microsoft.com/fwlink/?linkid=268687\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268687%26clcid=0xc0a)
        
        Para Exchange 2010, consulte "Set-UMIPGateway: Ayuda de Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=268688\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268688%26clcid=0xc0a).
    
      - Si utiliza la Consola de administración de Exchange, desactive la casilla **Permitir llamadas realizadas a través de esta puerta de enlace IP de MU**.
    
    > [!IMPORTANT]  
    > Si su plan de marcado del URI del SIP de Mensajería unificada está asociado a una única puerta de enlace IP, no impida que las llamadas realizadas pasen a través de esta puerta de enlace.
    


7.  Cree un operador automático de Mensajería unificada para cada uno de los planes de marcado de Lync Server.
    
    > [!IMPORTANT]  
    > No incluya espacios en el nombre del operador automático.
    
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "New-UMAutoAttendant: Ayuda de Exchange 2007" en [http://go.microsoft.com/fwlink/?linkid=268689\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268689%26clcid=0xc0a).
    
      - Para Exchange 2010, consulte "New-UMAutoAttendant: Ayuda de Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=268690\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268690%26clcid=0xc0a).
    
    El siguiente paso deberá realizarse para cada uno de los usuarios después de haber habilitado a los usuarios de Lync Server para Telefonía IP empresarial y conocer sus URI de SIP.

8.  Asocie los usuarios de Mensajería unificada de Exchange (cada uno de los cuales debe haberse configurado con un buzón de correo de Exchange) al plan de marcado de Mensajería unificada y cree un URI de SIP para cada usuario.
    

    > [!NOTE]
    > El <STRONG>SIPResourceIdentifier</STRONG> del siguiente ejemplo debe ser la dirección SIP del usuario de Lync Server.

    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    Para obtener más información, consulte:
    
      - Para Exchange 2007, consulte "Enable-UMMailbox: Ayuda de Exchange 2007" en [http://go.microsoft.com/fwlink/?linkid=268691\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268691%26clcid=0xc0a).
    
      - Para Exchange 2010, consulte "Enable-UMMailbox: Ayuda de Exchange 2010" en [http://go.microsoft.com/fwlink/?linkid=268692\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268692%26clcid=0xc0a).

