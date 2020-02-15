---
title: Configuración de la compatibilidad de Federación para un cliente de Skype empresarial online
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Si implementa Skype empresarial en su organización, puede federar a los dominios de uno o más clientes de Skype empresarial online. '
ms.openlocfilehash: b7488d21463782a978c9a3d6263d9fdfc2e59dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037290"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuración de la compatibilidad de Federación para un cliente de Skype empresarial online en Skype empresarial Server 

Puede proporcionar servicios de comunicaciones a usuarios de la organización de cualquiera de las siguientes maneras:

  - Implementar Skype empresarial Server en su organización (conocido como *servicios locales*) y configurar cuentas de usuario de Skype empresarial en su organización.
  - Configurar una cuenta de cliente de Microsoft Skype empresarial online con un proveedor de hospedaje y configurar cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).

Si implementa Skype empresarial en su organización, puede federar a los dominios de uno o más clientes de Skype empresarial online. Para habilitar la Federación entre los usuarios de su implementación local de Skype empresarial y los usuarios de un cliente de Skype empresarial online, debe configurar la compatibilidad con el dominio y los usuarios del cliente de Skype empresarial online.

> [!NOTE]  
> En esta documentación solo se describen los procedimientos para configurar su organización para que admita la Federación con un cliente de Skype empresarial online. En esta documentación no se describen los procedimientos para configurar el cliente de Skype empresarial online para que admita la Federación. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Requisitos previos para federar con un cliente de Skype empresarial online

Para federar con un cliente de Skype empresarial online, debe haber completado ya la implementación inicial y la configuración de Skype empresarial Server en la organización. Esto incluye lo siguiente:

  - Implementar al menos un servidor Standard Edition o un grupo de servidores front-end Enterprise Edition en la organización. 
  - Habilitación de cuentas de usuario internas para Skype empresarial Server. 
  - Implementar al menos un servidor perimetral y los otros componentes necesarios para admitir el acceso de usuarios externos. Para obtener más información, consulte [Managing Federation and external Access to Skype for Business Server](../managing-federation-and-external-access.md).
  - Habilitación de la compatibilidad de Federación dentro de la organización y configuración del método adecuado para controlar el acceso por parte de los dominios federados. Para obtener más información, consulte [enable or Disable Remote User Access](../access-edge/enable-or-disable-remote-user-access.md) and [Manage SIP Federated Providers for your Organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Habilitación del acceso de usuarios externos a los usuarios de la organización. Para obtener más información, consulte [asignar una directiva de acceso de usuario externo a un usuario habilitado para Skype empresarial](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurar la compatibilidad con la Federación para un dominio de Skype empresarial online

Para federar con un cliente de Skype empresarial online es necesario completar los siguientes pasos:

  - Configure la compatibilidad para el dominio del cliente 2010 de Skype empresarial online (por ejemplo, contoso.onmicrosoft.com). Como se especifica en [requisitos previos para federar con un cliente de Skype empresarial online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), debe haber habilitado la Federación de su organización. Para ello, se debe especificar el método que se usará para controlar el acceso por dominios federados. Si configuró su organización para que use detección, es opcional agregar el dominio a la lista permitida de su organización. Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Skype empresarial online a la lista de dominios permitidos. Puede Agregar un nombre de dominio mediante el panel de control de Skype empresarial Server o mediante la ejecución del cmdlet **New-CSAllowedDomain** . Para obtener información detallada sobre el uso del panel de control de Skype empresarial Server, incluida la habilitación de la detección de dominios, vea [Manage SIP Federated Providers for your Organization in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obtener información detallada sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, consulte [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Un cliente de Skype empresarial online puede tener varios dominios. Si desea federarse con más de uno de los dominios, debe configurar la compatibilidad para cada dominio con el que desee admitir la Federación, y el administrador del cliente de Skype empresarial online debe habilitar la Federación de cada uno de los dominios para estar federado.

  - Configure la compatibilidad para el proveedor de hospedaje del dominio del cliente de Skype empresarial online con el que quiera federar. Use el procedimiento de esta sección para configurar la compatibilidad para el proveedor de hospedaje.

    > [!NOTE]  
    > Este paso solo es necesario para la Federación con un dominio de un cliente de Skype empresarial online, no para la Federación con ningún dominio implementado localmente en la ubicación de un socio federado.


### <a name="to-configure-support-for-a-hosting-provider"></a>Para configurar compatibilidad para un proveedor de hospedaje

1.  En un servidor front-end, inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Skype empresarial Server**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2.  Ejecute el cmdlet de **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    En el ejemplo anterior se definen los parámetros siguientes:
    
      - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor existente con dicho valor de Identity.
    
      - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, usted tendrá que eliminar y volver a crear la entrada de dicho proveedor.
    
      - **VerificationLevel** indica de qué manera se comprueban (y si se comprueban) los mensajes enviados desde un proveedor de hospedaje para asegurar que se enviaron realmente desde dicho proveedor.
    
      - **Enabled** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.
    
      - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).
    
      - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Skype empresarial Server. Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.
    
      - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido en su topología de Skype empresarial Server.
    
    Para obtener más información sobre el uso de este cmdlet, consulte [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurar el acceso de usuario para la Federación con un cliente de Skype empresarial online 

Para que todos los usuarios de su organización puedan comunicarse con socios federados, debe configurar sus cuentas de usuario. Esta configuración se aplica a todos los socios federados, incluidos los dominios de clientes de Microsoft Skype empresarial online con los que admite la Federación. Para más información sobre cómo configurar la compatibilidad de Federación para las cuentas de usuario, vea [Configure Policies to control Federated User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md) y [assign a external User Access Policy to a Skype for Business Enabled User](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Comprobar las comunicaciones con un cliente de Skype empresarial online en Skype empresarial Server

Para permitir que los usuarios de Skype empresarial de su organización se comuniquen con los usuarios de un cliente de Skype empresarial online, debe haber completado los siguientes pasos:

  - Reunir todos los requisitos previos. Este paso incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con federación para la organización, y configurar cuentas de usuario. Para obtener más información, consulte [requisitos previos para federar con un cliente de Skype empresarial online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Configurar compatibilidad con acceso a dominio en la implementación interna. Esto incluye la creación de una entrada de proveedor de host y la configuración de la implementación para permitir el acceso desde el dominio del cliente de Skype empresarial online. Para obtener más información, consulte [configurar la compatibilidad con la Federación para un dominio de Skype empresarial online](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Configurar sus cuentas de usuario para admitir federación. Para obtener más información, consulte [configurar el acceso de usuario para la Federación con un cliente de Skype empresarial online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Después de completar todos estos pasos y el administrador del cliente de Skype empresarial online completa toda la configuración de sus servicios en línea para admitir la Federación con su organización, compruebe las comunicaciones probando las comunicaciones entre un usuario interno de su organización y un usuario del cliente de Skype empresarial online. Si la comunicación no se realiza correctamente, use la herramienta de registro del servidor perimetral para capturar los archivos de registro y de seguimiento con el fin de solucionar el problema. 
