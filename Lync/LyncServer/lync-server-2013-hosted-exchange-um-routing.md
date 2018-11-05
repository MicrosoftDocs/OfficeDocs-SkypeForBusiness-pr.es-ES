---
title: 'Lync Server 2013: Enrutamiento de mensajería unificada de Exchange hospedada'
TOCTitle: " Enrutamiento de mensajería unificada de Exchange hospedada"
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48275574
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enrutamiento de mensajería unificada de Exchange hospedada en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

La aplicación de enrutamiento de Mensajería unificada de Exchange se ejecuta en el Servidor front-end para enrutar llamadas, ya sea a una implementación local de mensajería unificada (MU) de Microsoft Exchange Server o a un servicio hospedado de Mensajería unificada de Exchange.

## La aplicación ExUM Routing

La aplicación de enrutamiento de Mensajería unificada de Exchange de Lync Server 2013 usa la información de la configuración de la cuenta de usuario y de los parámetros de la directiva de correo de voz hospedado para determinar cómo enrutar las llamadas para la mensajería de voz hospedada, tal y como se muestra en el siguiente diagrama.

**Ejemplo de implementación combinada del enrutamiento UM de Exchange**

![Implementación local de mensajería unificada de Lync Server Exchange](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "Implementación local de mensajería unificada de Lync Server Exchange")

El enrutamiento de la Mensajería unificada de Exchange se puede configurar para enrutar llamadas a usuarios con la Mensajería unificada de Exchange local habilitada, a usuarios con la Mensajería unificada de Exchange hospedada habilitada o una combinación de ambas opciones.

Por ejemplo, supongamos que el buzón de correo de Roy y el servicio de Mensajería unificada de Exchange están hospedados en una implementación local de Exchange.

  - La información de la dirección proxy de la cuenta de usuario de Roy contiene los datos que la aplicación de enrutamiento de mensajería unificada de Exchange usa para enrutar sus llamadas a un servidor de Mensajería unificada de Exchange local.

El buzón y el servicio de Mensajería unificada de Exchange de Alice se encuentran en un centro de datos del proveedor de servicios de Exchange hospedado. El enrutamiento de sus llamadas de Mensajería unificada de Exchange se configura de la siguiente forma:

  - Los valores establecidos en el atributo msExchUCVoiceMailSettings de la cuenta de usuario de Alicia le dice a la aplicación ExUM Routing que compruebe los detalles de enrutamiento en una directiva de correo de voz hospedado.
    

    > [!NOTE]
    > El valor del atributo msExchUCVoiceMailSettings puede establecerlo el proveedor de servicios de Exchange o el administrador de Lync Server 2013. En el ejemplo que se muestra en el diagrama anterior, el valor (CsHostedVoiceMail=1) lo había establecido el administrador de Lync Server 2013 para habilitar el correo de voz hospedado para Alice. Para obtener más información acerca de este atributo, consulte <A href="lync-server-2013-hosted-exchange-user-management.md">Administración de usuarios de Hosted Exchange en Lync Server 2013</A>.



  - La directiva de correo de voz hospedado que se ha asignado a la cuenta de usuario de Alicia proporciona la siguiente información de enrutamiento:
    
      - El destino es el proveedor de servicios de Mensajería unificada de Exchange hospedado (Is.ExUm. *\<hostedExchangeServer\>* .com en este ejemplo).
    
      - Las organizaciones se identifican mediante los identificadores de arrendatario, que son los FQDN de enrutamiento de los mensajes SIP para los arrendatarios de Exchange Server ubicados en Is.ExUm. *\<hostedExchangeServer\>* .com (corp.contoso.com y corp.litwareinc.com en este ejemplo).
        

        > [!NOTE]
        > El FQDN para Exchange Online es exap.um.outlook.com.

        
        Para ver información detallada, consulte [Directivas de correo de voz hospedado en Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).


> [!NOTE]
> Si tanto el atributo msExchUCVoiceMailSettings como la configuración de la dirección proxy de mensajería unificada están presentes en una cuenta de usuario, el atributo msExchUCVoiceMailSettings tendrá prioridad.


