---
title: Ver información del dispositivo de conferencias
TOCTitle: Ver información del dispositivo de conferencias
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994043(v=OCS.15)
ms:contentKeyID: 52061664
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver información del dispositivo de conferencias

 

_**Última modificación del tema:** 2013-02-20_

Para ver la información referente a los dispositivos de conferencia que están configurados en su organización, use el Windows PowerShell y el cmdlet **Get-CsMeetingRoom**. Ejecute el cmdlet **Get-CsMeetingRoom** desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



Si usa el cmdlet **Get-CsMeetingRoom** sin ningún parámetro, devuelve información sobre todos los dispositivos de conferencia. Con parámetros opcionales, la información se puede filtrar de diversos modos. Para más información, consulte la sección Parámetros de [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).


## Ver información sobre todos los dispositivos de conferencia

  - Para ver información sobre todos los dispositivos de conferencia, escriba el siguiente comando en el Shell de administración de Lync Server y después presione Entrar:
    
        Get-CsMeetingRoom
    
    Este cmdlet devuelve información similar a la siguiente en relación a cada dispositivo de conferencia. Tenga en cuenta que este ejemplo solo muestra parte de la información que verá cuando ejecute este cmdlet:
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

## Ver información sobre un dispositivo de conferencia concreto

  - Para ver información sobre un dispositivo de conferencia específico, incluya el parámetro Identidad seguido de la identidad del dispositivo de conferencia (generalmente, el nombre para mostrar de Active Directory). Por ejemplo:
    
        Get-CsMeetingRoom -Identity "Room 1219"

Para más información, consulte el tema de ayuda del cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom).

