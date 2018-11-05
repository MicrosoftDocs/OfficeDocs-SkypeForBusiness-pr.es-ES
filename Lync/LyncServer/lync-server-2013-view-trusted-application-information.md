---
title: Visualización de información de aplicaciones de confianza
TOCTitle: Visualización de información de aplicaciones de confianza
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49889242
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información de aplicaciones de confianza

 

_**Última modificación del tema:** 2015-03-30_

Use el siguiente procedimiento para ver la información de aplicaciones de confianza de Shell de administración de Lync Server 2013 en Shell de administración de Lync Server.

## Ver la información de aplicación de confianza al usar los cmdlets Shell de administración de Lync Server

Puede ver la información acerca de sus aplicaciones de confianza al usar Shell de administración de Lync Server y el cmdlet **Get-CsTrustedApplication**. Este cmdlet puede ejecutarse desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver las aplicaciones de confianza

  - Para ver todas sus aplicaciones de confianza, escriba el siguiente comando en el Shell de administración de Lync Server y luego presione ENTRAR:
    
        Get-CsConferenceDisclaimer
    
    Este comando devuelve información similar a la siguiente para cada aplicación de confianza:
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True

Para obtener detalles, vea [Get-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrustedApplication).

