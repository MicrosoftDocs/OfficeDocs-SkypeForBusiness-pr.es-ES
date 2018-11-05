---
title: "Crear objetos de contacto para la mensajería unificada de Exchange hospedada"
TOCTitle: Crear objetos de contacto para la mensajería unificada de Exchange hospedada
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48276182
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-24_

En el procedimiento siguiente se explica cómo crear objetos de contacto de operador automático o acceso de suscriptor para la mensajería unificada de Exchange hospedada.

Para obtener más información, consulte [Administración de objetos de contactos de Hosted Exchange en Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) en la documentación sobre planeamiento.

Para más información sobre la configuración de objetos de contacto, consulte la documentación de Shell de administración de Lync Server para los siguientes cmdlets:

  - [New-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExUmContact)

> [!IMPORTANT]  
> Para poder habilitar objetos de contacto de Lync Server 2013 para la mensajería unificada de Exchange hospedada, debe implementarse una directiva de correo de voz hospedada que se aplique a dichos objetos. Para más información, consulte <a href="lync-server-2013-hosted-voice-mail-policies.md">Directivas de correo de voz hospedado en Lync Server 2013</a>.



## Para crear objetos de contacto de operador automático o de acceso de suscriptor para mensajería unificada de Exchange hospedada

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet New-CsExUmContact para crear los objetos de contacto necesarios para su implementación. Por ejemplo, ejecute la línea siguiente para crear un objeto de contacto de operador automático o de acceso de suscriptor:
    
    ```
    New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
    ```
    ```
    New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
    ```
    
    En estos ejemplos se definen los parámetros siguientes:
    
      - **SipAddress** especifica la dirección SIP del objeto de contacto. Debe tratarse de una dirección que todavía no se haya usado para configurar un objeto de contacto o de usuario en los Servicios de dominio de Active Directory. Este valor debe estar en el formato “sip:\< *dirección SIP* \>“, tal y como se muestra en los ejemplos anteriores.
    
      - **RegistrarPool** especifica el nombre de dominio completo (FQDN) del grupo de servidores en el que se ejecuta el servicio de registrador.
        

        > [!NOTE]
        > Los objetos de contacto de mensajería unificada de Exchange no pueden moverse a grupos de servidores que formen parte de implementaciones de Lync Server 2013 anteriores a Lync Server 2013.

    
      - **OU** especifica la unidad organizativa de Active Directory donde se encontrará este objeto de contacto.
    
      - **DisplayNumber** especifica el número de teléfono del objeto de contacto. El número de teléfono de cada objeto de contacto debe ser único.
    
      - **AutoAttendant** especifica si el objeto de contacto es un operador automático. Un operador automático ofrece una serie de mensajes de voz que permiten a los autores de llamadas navegar por el sistema telefónico hasta llegar al punto deseado. En este parámetro el valor **False** (el predeterminado) indica un objeto de contacto de acceso de suscriptor.

