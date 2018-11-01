---
title: Configurar el servicio de correo de voz en la nube
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instrucciones de implementación de voz basados en la nube para los usuarios alojados en Skype para Business Server.
ms.openlocfilehash: 05c486ed338e8e77ab68f12a64c3a59646a157d0
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838749"
---
# <a name="configure-cloud-voicemail-service"></a>Configurar el servicio de correo de voz en la nube

## <a name="overview"></a>Información general 
En este artículo se describe cómo configurar el servicio de correo de voz de Microsoft en la nube para su Skype para los usuarios empresariales locales.  

En este artículo se supone que ya dispone de Skype para Business Server implementado en una topología admitida y que cumplen los requisitos previos para la configuración de conectividad híbrida.

Para obtener más información acerca de las ventajas, planeación, requisitos y consideraciones para la implementación de correo de voz en la nube, vea [servicio de planeación de correo de voz en la nube](plan-cloud-voicemail.md).




Configuración de correo de voz en la nube implica las siguientes tareas:

1.  Asegúrese de que se cumplen los requisitos previos tal como se describe en el [servicio de planeación de correo de voz en la nube](plan-cloud-voicemail.md).

2.  Asegúrese de que ha configurado la conectividad híbrida tal como se describe en [conectividad híbrida de Plan](plan-hybrid-connectivity.md) y [conectividad de la configuración híbrida](configure-hybrid-connectivity.md). 

3.  [Configuración de correo de voz en la nube como el proveedor de hospedaje en el servidor perimetral](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) tal como se describe en este artículo.

4.  [Configure una directiva de correo de voz hospedado](#configure-a-hosted-voicemail-policy) como se describe en este artículo.

5.  [Asignar una directiva de correo de voz hospedado](#assign-a-hosted-voicemail-policy) como se describe en este artículo.

6.  [Habilitar a un usuario de correo de voz en la nube](#enable-a-user-for-cloud-voicemail) tal como se describe en este artículo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Configurar el correo de voz en la nube como el proveedor de hospedaje en el servidor perimetral 

Configurar el correo de voz en la nube como el proveedor de hospedaje en el servidor perimetral mediante el cmdlet New-CsHostingProvider con los siguientes parámetros:

- **Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear; Por ejemplo, en la nube correo de voz. 

- **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. Este parámetro debe establecerse en True.

- **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se usará en un escenario de espacio de direcciones SIP compartido. Este parámetro debe establecerse en True.

- **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Skype para las cuentas de Business Server. Este parámetro debe establecerse en False.

- **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy utilizado por el proveedor de hospedaje; Por ejemplo, proxyserver.contoso.com. Para obtener esta información, póngase en contacto con su proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia su servidor proxy, debe eliminar y, a continuación, volver a crear la entrada de ese proveedor.

- **IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype de topología de servidores de negocio. Este parámetro debe establecerse en False.

Por ejemplo, en Skype para el shell de administración de negocio, el siguiente cmdlet configura el correo de voz en la nube como el proveedor de hospedaje:


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar una directiva de correo de voz hospedado

Para asegurarse de que correo de voz para su organización se enruta al servicio de correo de voz en la nube, debe configurar una directiva de correo de voz hospedado para su organización. En muchos casos, solo un correo de voz hospedado directiva es necesario y se puede modificar la directiva global para satisfacer todas sus necesidades. Si la organización requiere varias directivas de correo de voz hospedado, puede agregar las directivas mediante el cmdlet new-cshostedvoicemailpolicy.

Para modificar la directiva global, ejecute el siguiente comando en el Skype para Business Server shell de administración de después de actualizar la organización y TenantID:

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **Destino** especifica el nombre de dominio completo (FQDN) del servicio hospedado de correo de voz en la nube. Este valor debe establecerse en **exap.um.outlook.com**.

- **Organización** es el dominio predeterminado asignado a su inquilino. Puede recuperar esta información mediante la necesidad de la administración de inquilinos inicie sesión office.com, haga clic en la aplicación de centro de administración, navegue hasta **el programa de instalación** de la izquierda y haga clic en **dominios**. Por ejemplo: mytenant.onmicrosoft.com.

    El nombre de la organización también es el nombre de dominio predeterminado en Office 365.

- **TenantID** se usa para identificar al inquilino de Office 365. Para obtener más información, vea [encontrar el identificador del inquilino de Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Para asegurarse de que una directiva de correo de voz hospedado se creó correctamente, ejecute el siguiente comando:

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Asignar una directiva de correo de voz hospedado

De forma predeterminada, la Global hospedada directiva de correo de voz se asigna a todos los usuarios. Si utiliza una directiva diferente, antes de habilitar a los usuarios para correo de voz hospedado, primero debe conceder a los usuarios la directiva de correo de voz hospedado que desee mediante el cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Por ejemplo, el comando siguiente asigna una directiva de correo de voz hospedado no Global a un usuario:


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar a un usuario de correo de voz en la nube

Para habilitar las llamadas de correo de voz de un usuario deben enrutarse al correo de voz en la nube, usar el cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con el parámetro HostedVoiceMail. 

Por ejemplo, el siguiente comando permite una cuenta de usuario de correo de voz en la nube: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

El cmdlet comprueba que una directiva de correo de voz en la nube--a nivel global, nivel de sitio o usuario--se aplica a este usuario. Si no se aplica ninguna directiva, se produce un error en el cmdlet.  

En el ejemplo siguiente se deshabilita una cuenta de usuario de correo de voz en la nube:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

El cmdlet comprueba que no hay ninguna directiva de correo de voz hospedado--a nivel global, nivel de sitio o usuario--se aplica a este usuario. Si se aplica una directiva, se produce un error en el cmdlet.

> [!NOTE]
>  Los usuarios deben ser habilitada para usar el servicio de correo de voz de Microsoft en la nube de telefonía IP empresarial.