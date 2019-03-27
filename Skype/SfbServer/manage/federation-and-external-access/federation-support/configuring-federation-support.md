---
title: Configuración de la compatibilidad de federación para un cliente de Skype Empresarial Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Si implementa Skype para la empresa en su organización, puede federar con los dominios de uno o más Skype para clientes empresariales en línea. '
ms.openlocfilehash: 70eda58c5d01b09c9f3e00ef8f3ac0391a90ed07
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899725"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuración de compatibilidad con la federación para un Skype para clientes empresariales en línea en Skype para Business Server 

Puede proporcionar servicios de comunicaciones a los usuarios de la organización en cualquiera de las siguientes maneras:

  - Implementación de Skype para Business Server en la organización (conocido como *Servicios de local*) y la configuración de Skype para cuentas de usuario de negocio en la organización.
  - Configurar un Skype Microsoft para la cuenta del cliente en línea de negocio con un proveedor de hospedaje y configuración de cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).

Si implementa Skype para la empresa en su organización, puede federar con los dominios de uno o más Skype para clientes empresariales en línea. Para habilitar la federación entre los usuarios de su Skype local para la implementación de la empresa y los usuarios de un Skype para clientes empresariales en línea, debe configurar la compatibilidad con el dominio y los usuarios de la Skype para clientes empresariales en línea.

> [!NOTE]  
> Esta documentación describe sólo los procedimientos para configurar su organización para admitir la federación con un Skype para clientes empresariales en línea. Esta documentación se describen los procedimientos para configurar el Skype para clientes empresariales en línea admitir la federación. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Requisitos previos para federar con un Skype para clientes empresariales en línea

Para federarse con un Skype para clientes empresariales en línea, se deben haber completado la implementación inicial y la configuración de Skype para Business Server en la organización. Entre estas directivas se incluyen:

  - Implementación de al menos un servidor Standard Edition o un grupo de servidores Front-End de Enterprise Edition en su organización. 
  - Habilitar cuentas de usuario interno de Skype para Business Server. 
  - Implementación de al menos un servidor perimetral y los demás componentes necesarios para admitir el acceso de usuarios externos. Para obtener información detallada, vea [Managing federación y el acceso externo a Skype para Business Server](../managing-federation-and-external-access.md).
  - Habilitar compatibilidad con la federación dentro de la organización y configurar el método adecuado para controlar el acceso de los dominios federados. Para obtener información detallada, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md) y [Administrar SIP federados proveedores para su organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Habilitar el acceso de usuarios externos para los usuarios de su organización. Para obtener información detallada, vea [asignar una directiva de acceso de usuarios externos para un Skype para profesionales de usuario habilitada](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurar la compatibilidad de federación con un Skype para el dominio de negocio en línea

Federación con un Skype para clientes empresariales en línea, es necesario para llevar a cabo los siguientes pasos:

  - Configurar la compatibilidad con el dominio de la Skype para 2010 en línea de negocio de cliente (por ejemplo, contoso.onmicrosoft.com). Tal como se especifica en [los requisitos previos para federar con un Skype para clientes empresariales en línea](#prerequisites-for-federating-with-a-skype-for-business-online-customer), debe ha habilitado la federación para su organización. Habilitación de la federación requiere que especifica el método que debe usar para controlar el acceso de los dominios federados. Si ha configurado la organización para usar la detección, agregar el dominio a la lista permitidos de la organización es opcional. Si no habilitó la detección de dominio, debe agregar el nombre de dominio de la Skype para clientes empresariales en línea a la lista de dominios permitidos. Puede agregar un nombre de dominio mediante el uso de Skype para el Panel de Control de servidor empresarial o ejecutando el cmdlet **New-CSAllowedDomain** . Para obtener información detallada acerca del uso de Skype para el Panel de Control de servidor empresarial, incluida la activación de la detección de dominios, vea [Administrar SIP proveedores para su organización en Skype para Business Server federados](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obtener información detallada sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, vea [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un Skype para clientes empresariales en línea puede tener varios dominios. Si desea establecer una federación con más de uno de los dominios, debe configurar la compatibilidad con cada dominio con el que desea admitir la federación y el Administrador de la Skype para clientes empresariales en línea debe habilitar la federación para cada uno de los dominios a se federados.

  - Configurar la compatibilidad con el proveedor de hospedaje de la Skype para el dominio de cliente en línea de negocio con la que desee federarse. Use el procedimiento de esta sección para configurar la compatibilidad con el proveedor de hospedaje.

    > [!NOTE]  
    > Este paso es necesario solamente para la federación con un dominio de un Skype para clientes empresariales en línea, no para la federación con cualquier dominio que se implementa localmente en la ubicación de un socio federado.


### <a name="to-configure-support-for-a-hosting-provider"></a>Para configurar la compatibilidad con un proveedor de hospedaje

1.  Desde un servidor Front-End, inicie el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.

2.  Ejecute el cmdlet **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identidad** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor con dicho valor de Identity.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **VerificationLevel** especifica cómo (o si) se comprobarán los mensajes enviados desde un proveedor de hospedaje para asegurarse de que se enviaron desde dicho proveedor.
    
      - **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True **.
    
      - **EnabledSharedAddressSpace ** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Skype para las cuentas de Business Server. Si es **False **, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **IsLocal** indica si el servidor proxy utilizado por el proveedor de hospedaje está dentro de su Skype de topología de servidores de negocio.
    
    Para obtener información detallada sobre el uso de este cmdlet, vea [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurar el acceso de usuarios para la federación con un Skype para clientes empresariales en línea 

El usuario debe configurar las cuentas de todos los usuarios de la organización en orden para ellos se les permite comunicarse con los socios federados. Esta configuración se aplica para todos los socios federados, incluidos cualquier Skype Microsoft para dominios de atención al cliente en línea de negocio con la que admitir la federación. Para obtener información detallada acerca de cómo configurar la compatibilidad con la federación para las cuentas de usuario, vea [Configurar directivas de control de acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md) y [asignar una directiva de acceso de usuarios externos para un Skype para profesionales de usuario habilitada](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Comprobar las comunicaciones con un Skype para clientes empresariales en línea en Skype para Business Server

Para habilitar Skype para que usuarios profesionales de la organización para comunicarse con los usuarios de un Skype para clientes empresariales en línea, debe haber completado los pasos siguientes:

  - Cumplir todos los requisitos previos. Esto incluye la implementación de su interna y servidores perimetrales, habilitar la federación de soporte técnico para la organización y cómo configurar cuentas de usuario. Para obtener información detallada, vea [requisitos previos para federar con un Skype para clientes empresariales en línea](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Configurar la compatibilidad con el acceso de dominio en la implementación interna. Esto incluye la creación de una entrada de proveedor de host y configuración de su implementación para permitir el acceso desde la Skype para el dominio del cliente en línea de negocio. Para obtener información detallada, vea [Configure la federación admitir para un Skype para dominio empresarial en línea](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configurar las cuentas de usuario para admitir la federación. Para obtener información detallada, vea [Configurar el acceso de usuarios para la federación con un Skype para clientes empresariales en línea](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Después de completar todos estos pasos y el Administrador de la Skype para clientes empresariales en línea complete toda la configuración de sus servicios en línea para admitir la federación con su organización, comprobar las comunicaciones mediante la comprobación de las comunicaciones entre un usuario interno en la organización y un usuario de la Skype para clientes empresariales en línea. Si la comunicación no se realiza correctamente, use la herramienta de registro de su servidor perimetral para capturar archivos de registro y seguimiento para solucionar el problema. 
