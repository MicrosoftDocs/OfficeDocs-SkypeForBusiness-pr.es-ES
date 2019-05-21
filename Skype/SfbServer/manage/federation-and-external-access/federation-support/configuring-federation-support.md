---
title: Configuración de la compatibilidad de federación para un cliente de Skype Empresarial Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Si implementa Skype empresarial en su organización, puede federar a los dominios de uno o más clientes de Skype empresarial online. '
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280113"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuración de la compatibilidad de Federación para un cliente de Skype empresarial online en Skype empresarial Server 

Puede proporcionar servicios de comunicaciones a los usuarios de su organización de cualquiera de las siguientes maneras:

  - Implementar Skype empresarial Server en su organización (conocido como *servicio local*) y configurar cuentas de usuario de Skype empresarial en su organización.
  - Configurar una cuenta de cliente de Microsoft Skype empresarial online con un proveedor de hospedaje y configurar cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).

Si implementa Skype empresarial en su organización, puede federar a los dominios de uno o más clientes de Skype empresarial online. Para habilitar la Federación entre los usuarios de su implementación local de Skype empresarial y los usuarios de un cliente de Skype empresarial online, debe configurar la compatibilidad con el dominio y los usuarios del cliente de Skype empresarial online.

> [!NOTE]  
> Esta documentación describe solo los procedimientos para configurar su organización con el fin de que admita la Federación con un cliente de Skype empresarial online. En esta documentación no se describen los procedimientos para configurar el cliente de Skype empresarial online para que admita la Federación. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Requisitos previos para la Federación con un cliente de Skype empresarial online

Para federarse a un cliente de Skype empresarial online, ya debe haber completado la implementación inicial y la configuración de Skype empresarial Server en su organización. Entre estas directivas se incluyen:

  - Implementar al menos un servidor Standard Edition o un grupo de servidores front-end Enterprise Edition en la organización. 
  - Habilitar cuentas de usuario internas para Skype empresarial Server. 
  - Implementar al menos un servidor perimetral y los otros componentes necesarios para admitir el acceso de usuarios externos. Para obtener más información, consulte [administrar la Federación y el acceso externo a Skype empresarial Server](../managing-federation-and-external-access.md).
  - Habilitar la compatibilidad de Federación dentro de su organización y configurar el método adecuado para controlar el acceso por parte de los dominios federados. Para obtener más información, vea [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md) y [administrar proveedores federados de SIP para su organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Habilitar el acceso de usuarios externos a los usuarios de su organización. Para obtener más información, consulte [asignar una directiva de acceso de usuarios externos a un usuario habilitado para Skype empresarial](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurar la compatibilidad de Federación para un dominio de Skype empresarial online

La Federación con un cliente de Skype empresarial online requiere que complete los pasos siguientes:

  - Configurar la compatibilidad del dominio del cliente de Skype empresarial online 2010 (por ejemplo, contoso.onmicrosoft.com). Como se especifica en los [requisitos previos para la Federación con un cliente de Skype empresarial online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), ya debe haber habilitado la Federación de su organización. Habilitar la Federación requiere especificar el método que se va a usar para controlar el acceso de los dominios federados. Si ha configurado su organización para usar la detección, agregar el dominio a la lista de permitidos de la organización es opcional. Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Skype empresarial online a la lista de dominios permitidos. Puede Agregar un nombre de dominio mediante el panel de control de Skype empresarial Server o ejecutando el cmdlet **New-CSAllowedDomain** . Para obtener detalles sobre el uso del panel de control de Skype empresarial Server, incluido el descubrimiento de dominios, consulte [administrar proveedores federados SIP para su organización en Skype empresarial Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obtener más información sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, consulte [New-CSAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un cliente de Skype empresarial online puede tener varios dominios. Si desea federar con más de uno de los dominios, debe configurar la compatibilidad para cada dominio con el que desee admitir la Federación, y el administrador del cliente de Skype empresarial online debe habilitar la Federación de cada uno de los dominios para estar federado.

  - Configure la compatibilidad para el proveedor de hospedaje del dominio de cliente de Skype empresarial online con el que desea federarse. Use el procedimiento de esta sección para configurar la compatibilidad con el proveedor de hospedaje.

    > [!NOTE]  
    > Este paso solo es necesario para la Federación con un dominio de un cliente de Skype empresarial online, no para la Federación con cualquier dominio que se implemente localmente en la ubicación de un socio federado.


### <a name="to-configure-support-for-a-hosting-provider"></a>Para configurar la compatibilidad con un proveedor de hospedaje

1.  Desde un servidor front-end, inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, a continuación, haga clic en **consola de administración de Skype empresarial**.

2.  Ejecute el cmdlet **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que está creando. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor con dicho valor de Identity.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy usado por el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **VerificationLevel** especifica cómo (o si) se comprueban los mensajes enviados desde un proveedor de hospedaje para asegurarse de que se han enviado desde ese proveedor.
    
      - **Habilitada ** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True **.
    
      - **EnabledSharedAddressSpace ** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Skype empresarial Server. Si es **False **, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido dentro de la topología de su servidor de Skype empresarial.
    
    Para obtener más información sobre el uso de este cmdlet, vea [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurar el acceso de usuarios para la Federación con un cliente de Skype empresarial online 

Debe configurar las cuentas de usuario de todos los usuarios de la organización para que se les permita comunicarse con los socios federados. Esta configuración se aplica a todos los socios federados, incluidos los dominios de cliente de Microsoft Skype empresarial online con los que admite la Federación. Para obtener detalles sobre la configuración de la compatibilidad de Federación para cuentas de usuario, vea [configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md) y [asignar una directiva de acceso de usuarios externos a un usuario habilitado para Skype empresarial](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Comprobar las comunicaciones con un cliente de Skype empresarial online en Skype empresarial Server

Para permitir que los usuarios de Skype empresarial de su organización se comuniquen con los usuarios de un cliente de Skype empresarial online, debe haber completado los siguientes pasos:

  - Cumple con todos los requisitos previos. Esto incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con la Federación de su organización y configurar cuentas de usuario. Para obtener más información, consulte [requisitos previos para federar con un cliente de Skype empresarial online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Compatibilidad con el acceso a dominios configurado en la implementación interna. Esto incluye la creación de una entrada de proveedor de host y la configuración de la implementación para permitir el acceso desde el dominio del cliente de Skype empresarial online. Para obtener más información, vea [configurar la compatibilidad de Federación para un dominio de Skype empresarial online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configuró las cuentas de usuario para admitir la Federación. Para obtener más información, vea [configurar el acceso de usuarios para la Federación con un cliente de Skype empresarial online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Después de completar todos estos pasos y el administrador del cliente de Skype empresarial online completa toda la configuración de sus servicios en línea para admitir la Federación con su organización, comprobar las comunicaciones entre una usuario interno de su organización y un usuario del cliente de Skype empresarial online. Si la comunicación no se realiza correctamente, use la herramienta de registro de su servidor perimetral para capturar archivos de registro y de seguimiento a fin de solucionar el problema. 
