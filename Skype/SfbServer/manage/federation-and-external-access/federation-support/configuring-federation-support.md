---
title: Configuración de la compatibilidad de federación para un cliente de Skype Empresarial Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Si implementas Skype Empresarial en la organización, puedes federar con los dominios de uno o más Skype Empresarial online. '
ms.openlocfilehash: c8e0481a85ff371e5454856d5b84a4dbccf50a97
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240534"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configurar la compatibilidad de federación para un cliente Skype Empresarial Online en Skype Empresarial Server

Puede proporcionar servicios de comunicaciones a usuarios de la organización de cualquiera de las siguientes maneras:

- Implementar Skype Empresarial Server en la organización (conocidos como servicios *locales)* y configurar Skype Empresarial cuentas de usuario de la organización.
- Configurar una cuenta de cliente de Microsoft Skype Empresarial Online con un proveedor de hospedaje y configurar cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea).*

Si implementas Skype Empresarial en la organización, puedes federar con los dominios de uno o más Skype Empresarial online. Para habilitar la federación entre los usuarios de la implementación Skype Empresarial local y los usuarios de un cliente de Skype Empresarial Online, debe configurar la compatibilidad con el dominio y los usuarios del cliente de Skype Empresarial Online.

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> En esta documentación se describen solo los procedimientos para configurar la organización para admitir la federación con un Skype Empresarial online. En esta documentación no se describen los procedimientos para configurar el cliente Skype Empresarial Online para admitir la federación.

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Requisitos previos para federar con un Skype Empresarial online

Para federar con un cliente de Skype Empresarial Online, ya debería haber completado la implementación inicial y la configuración de Skype Empresarial Server en la organización. Esto incluye lo siguiente:

- Implementar al menos un servidor Standard Edition servidor o Enterprise Edition grupo de servidores front-end de la organización.
- Habilitar cuentas de usuario internas para Skype Empresarial Server.
- Implementar al menos un servidor perimetral y los demás componentes necesarios para admitir el acceso de usuarios externos. Para obtener más información, vea [Managing federation and external access to Skype Empresarial Server](../managing-federation-and-external-access.md).
- Habilitar la compatibilidad con la federación en la organización y configurar el método adecuado para controlar el acceso por dominios federados. Para obtener más información, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md) y Administrar proveedores [federados SIP para su organización.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
- Habilitar el acceso de usuarios externos para los usuarios de la organización. Para obtener más información, vea Asignar una directiva de acceso de usuario [externo a Skype Empresarial usuario habilitado.](../external-access-policies/assign-an-external-user-access-policy.md)

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configurar la compatibilidad de federación para un Skype Empresarial online

La federación con un cliente Skype Empresarial online requiere que complete los pasos siguientes:

- Configure la compatibilidad con el dominio del cliente de Skype Empresarial Online 2010 (por ejemplo, contoso.onmicrosoft.com). Como se especifica en [Requisitos previos](#prerequisites-for-federating-with-a-skype-for-business-online-customer)para federar con un cliente de Skype Empresarial Online, ya debería haber habilitado la federación para su organización. Para ello, se debe especificar el método que se usará para controlar el acceso por dominios federados. Si configuró su organización para que use detección, es opcional agregar el dominio a la lista permitida de su organización. Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Skype Empresarial Online a la lista de dominios permitidos. Puede agregar un nombre de dominio mediante Skype Empresarial Server panel de control o ejecutando el cmdlet **New-CSAllowedDomain.** Para obtener más información sobre Skype Empresarial Server panel de control, incluida la habilitación de la detección de dominios, vea [Manage SIP federated providers for your organization in Skype Empresarial Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obtener más información sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, vea [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

  > [!NOTE]  
  > Un Skype Empresarial online puede tener varios dominios. Si desea federar con más de uno de los dominios, debe configurar la compatibilidad para cada dominio individual con el que desea admitir la federación y el administrador del cliente de Skype Empresarial Online debe habilitar la federación para cada uno de los dominios que se va a federar.

- Configure la compatibilidad con el proveedor de hospedaje del Skype Empresarial cliente en línea con el que desea federar. Use el procedimiento de esta sección para configurar la compatibilidad para el proveedor de hospedaje.

  > [!NOTE]  
  > Este paso solo es necesario para la federación con un dominio de un cliente de Skype Empresarial Online, no para la federación con ningún dominio que se implemente localmente en la ubicación de un partner federado.

### <a name="to-configure-support-for-a-hosting-provider"></a>Para configurar compatibilidad para un proveedor de hospedaje

1. Desde un servidor front-end, inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** haga clic en Todos los **programas,** haga clic en **Skype Empresarial Server** y, a continuación, haga clic en Skype Empresarial Server Shell **de administración**.

2. Ejecute el cmdlet de **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute:

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    En el ejemplo anterior se definen los parámetros siguientes:

    - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor existente con dicho valor de Identity.

    - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, usted tendrá que eliminar y volver a crear la entrada de dicho proveedor.

    - **VerificationLevel** indica de qué manera se comprueban (y si se comprueban) los mensajes enviados desde un proveedor de hospedaje para asegurar que se enviaron realmente desde dicho proveedor.

    - **Enabled** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.

    - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).

    - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar Skype Empresarial Server cuentas. Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.

    - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está contenido en la topología Skype Empresarial Server cliente.

    Para obtener más información sobre el uso de este cmdlet, [vea New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configurar el acceso de usuario para la federación con un Skype Empresarial online

Para que todos los usuarios de su organización puedan comunicarse con socios federados, debe configurar sus cuentas de usuario. Esta configuración se aplica a todos los socios federados, incluidos los dominios de cliente de Microsoft Skype Empresarial Online con los que admita la federación. Para obtener más información sobre cómo configurar la compatibilidad de federación para cuentas de usuario, vea [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md) y Assign an external user access policy to a Skype Empresarial enabled [user](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Compruebe las comunicaciones con un cliente Skype Empresarial Online en Skype Empresarial Server

Para permitir que Skype Empresarial usuarios de la organización se comuniquen con los usuarios de un cliente de Skype Empresarial Online, debe haber completado los siguientes pasos:

- Reunir todos los requisitos previos. Este paso incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con federación para la organización, y configurar cuentas de usuario. Para obtener más información, vea [Prerequisites for federating with a Skype Empresarial Online customer](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
- Configurar compatibilidad con acceso a dominio en la implementación interna. Esto incluye la creación de una entrada de proveedor de host y la configuración de la implementación para permitir el acceso desde Skype Empresarial dominio del cliente en línea. Para obtener más información, vea [Configure federation support for a Skype Empresarial Online domain](#configure-federation-support-for-a-skype-for-business-online-domain).
- Configurar sus cuentas de usuario para admitir federación. Para obtener más información, vea [Configure user access for federation with a Skype Empresarial Online customer](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Después de completar todos estos pasos y de que el administrador del cliente de Skype Empresarial Online complete toda la configuración de sus servicios en línea para admitir la federación con su organización, compruebe las comunicaciones probando las comunicaciones entre un usuario interno de su organización y un usuario del cliente de Skype Empresarial Online. Si la comunicación no se realiza correctamente, use la Herramienta de registro desde el servidor perimetral para capturar archivos de registro y seguimiento con el fin de solucionar el problema.
