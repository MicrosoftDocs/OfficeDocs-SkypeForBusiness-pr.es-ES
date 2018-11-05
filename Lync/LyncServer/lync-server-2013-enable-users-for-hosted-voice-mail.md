---
title: "Lync Server 2013 : Activ. des utilisateurs pour la messagerie vocale hébergée"
TOCTitle: Habilitar a los usuarios para el correo de voz hospedado
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48277229
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-24_

Siga el procedimiento para que los usuarios de Lync Server 2013 queden habilitados para correo de voz en un servicio de mensajería unificada hospedada de Exchange.

Para obtener información detallada, vea [Administración de usuarios de Hosted Exchange en Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) en la documentación sobre planeamiento.

Para ver los detalles sobre el cmdlet [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser), consulte la documentación de Shell de administración de Lync Server.

> [!IMPORTANT]  
> Antes de habilitar a un usuario de Lync Server 2013 para correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a su cuenta de usuario. Para obtener información detallada, vea <a href="lync-server-2013-hosted-voice-mail-policies.md">Directivas de correo de voz hospedado en Lync Server 2013</a>.



## Para habilitar a los usuarios para correo de voz hospedado.

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsUser para configurar la cuenta del usuario para correo de voz hospedado. Por ejemplo, ejecute lo siguiente:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **HostedVoiceMail** permite que las llamadas de correo de voz de un usuario se enruten a una versión hospedada de mensajería instantánea de Exchange. También indica a Microsoft Lync 2013 que encienda el indicador de “Llamar al correo de voz”.
    
      - **Identity** especifica la cuenta de usuario que modificar. El valor de Identity puede especificarse con cualquiera de los formatos a continuación:
        
          - La dirección SIP del usuario
        
          - El nombre principal de usuario de Active Directory del usuario
        
          - El nombre con formato dominio\\nombre del usuario (por ejemplo, contoso\\kenmyer)
        
          - El nombre para mostrar de Servicios de dominio de Active Directory (por ejemplo, Ken Myer). Si usa el nombre para mostrar como valor de Identity, puede usar el asterisco (\*) como carácter comodín. Por ejemplo, el parámetro Identity "\* Smith" devuelve todos los usuarios con un nombre para mostrar que termina con el valor de cadena de caracteres "Smith".
        

        > [!NOTE]
        > El nombre de cuenta SAM de Active Directory del usuario no se puede usar como valor de Identity porque puede que no sea único en el bosque.


