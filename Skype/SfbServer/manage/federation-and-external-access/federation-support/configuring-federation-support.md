---
title: Configuración de la compatibilidad de federación para un cliente de Skype Empresarial Online
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Si implementa Skype Empresarial en su organización, puede federar con los dominios de uno o varios clientes de Skype Empresarial Online. '
ms.openlocfilehash: d180de014c0a7479eb5dc7a6fb60e00e5b136f24
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676232"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Configuración del soporte técnico de federación para un cliente de Skype Empresarial Online en Skype Empresarial Server

Puede proporcionar servicios de comunicaciones a usuarios de la organización de cualquiera de las siguientes maneras:

- Implementar Skype Empresarial Server en la organización (*conocidos como servicios locales*) y configurar Skype Empresarial cuentas de usuario en la organización.
- Configurar una cuenta de cliente de Microsoft Skype Empresarial Online con un proveedor de hospedaje y configurar cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).

Si implementa Skype Empresarial en su organización, puede federar con los dominios de uno o varios clientes de Skype Empresarial Online. Para habilitar la federación entre los usuarios de la implementación de Skype Empresarial local y los usuarios de un cliente de Skype Empresarial Online, debe configurar el soporte técnico para el dominio y los usuarios del cliente de Skype Empresarial Online.

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> En esta documentación se describen solo los procedimientos para configurar su organización para admitir la federación con un cliente de Skype Empresarial Online. En esta documentación no se describen los procedimientos para configurar el cliente de Skype Empresarial Online para admitir la federación.

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Requisitos previos para federar con un cliente de Skype Empresarial Online

Para federarse con un cliente de Skype Empresarial Online, ya debería haber completado la implementación inicial y la configuración de Skype Empresarial Server en su organización. Esto incluye lo siguiente:

- Implementar al menos un servidor Standard Edition o uno Enterprise Edition grupo de servidores front-end de la organización.
- Habilitación de cuentas de usuario internas para Skype Empresarial Server.
- Implementar al menos un servidor perimetral y los demás componentes necesarios para admitir el acceso de usuarios externos. Para obtener más información, consulte [Administración de federación y acceso externo a Skype Empresarial Server](../managing-federation-and-external-access.md).
- Habilitar la compatibilidad con la federación dentro de la organización y configurar el método adecuado para controlar el acceso por dominios federados. Para obtener más información, consulte [Habilitación o deshabilitación del acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md) y [Administración de proveedores federados SIP para su organización](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
- Habilitación del acceso de usuarios externos para los usuarios de la organización. Para obtener más información, consulte [Asignación de una directiva de acceso de usuario externo a un usuario habilitado para Skype Empresarial](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Configuración de la compatibilidad con la federación para un dominio de Skype Empresarial Online

La federación con un cliente de Skype Empresarial Online requiere que complete los pasos siguientes:

- Configure la compatibilidad con el dominio del cliente de Skype Empresarial Online 2010 (por ejemplo, contoso.onmicrosoft.com). Como se especifica en [Requisitos previos para federar con un cliente de Skype Empresarial Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer), ya debe haber habilitado la federación para su organización. Para ello, se debe especificar el método que se usará para controlar el acceso por dominios federados. Si configuró su organización para que use detección, es opcional agregar el dominio a la lista permitida de su organización. Si no ha habilitado la detección de dominios, debe agregar el nombre de dominio del cliente de Skype Empresarial Online a la lista de dominios permitidos. Puede agregar un nombre de dominio mediante Skype Empresarial Server Panel de control o ejecutando el cmdlet **New-CSAllowedDomain**. Para obtener más información sobre el uso de Skype Empresarial Server Panel de control, incluida la habilitación de la detección de dominios, consulte [Administración de proveedores federados SIP para su organización en Skype Empresarial Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Para obtener más información sobre cómo usar el cmdlet **New-CSAllowedDomain** para agregar un dominio, vea [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain).

  > [!NOTE]  
  > Un cliente de Skype Empresarial Online puede tener varios dominios. Si desea federar con más de uno de los dominios, debe configurar la compatibilidad con cada dominio individual con el que desea admitir la federación y el administrador del cliente de Skype Empresarial Online debe habilitar la federación para cada uno de los dominios para que se federe.

- Configure la compatibilidad con el proveedor de hospedaje del dominio de cliente de Skype Empresarial Online con el que desea federar. Use el procedimiento de esta sección para configurar la compatibilidad para el proveedor de hospedaje.

  > [!NOTE]  
  > Este paso solo es necesario para la federación con un dominio de un cliente de Skype Empresarial Online, no para la federación con ningún dominio que se implemente localmente en la ubicación de un asociado federado.

### <a name="to-configure-support-for-a-hosting-provider"></a>Para configurar compatibilidad para un proveedor de hospedaje

1. Desde un servidor front-end, inicie el shell de administración de Skype Empresarial Server: haga clic en **Inicio**, en **Todos los programas**, en **Skype Empresarial Server** y, a continuación, en **Skype Empresarial Server Shell de administración**.

2. Ejecute el cmdlet de **New-CsHostingProvider** para crear y configurar el proveedor de hospedaje. Por ejemplo, ejecute lo siguiente:

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    En el ejemplo anterior se definen los parámetros siguientes:

    - **Identity** especifica un identificador de valor de cadena único para el proveedor de hospedaje que va a crear. Tenga en cuenta que el comando no se completará correctamente si ya se ha configurado un proveedor existente con dicho valor de Identity.

    - **ProxyFQDN** especifica el nombre de dominio completo (FQDN) para el servidor proxy que usa el proveedor de hospedaje. Este valor no puede modificarse. Si el proveedor de hospedaje cambia de servidor proxy, usted tendrá que eliminar y volver a crear la entrada de dicho proveedor.

    - **VerificationLevel** indica de qué manera se comprueban (y si se comprueban) los mensajes enviados desde un proveedor de hospedaje para asegurar que se enviaron realmente desde dicho proveedor.

    - **Enabled** indica si la conexión de red entre el dominio y el proveedor de hospedaje está habilitada. No se pueden intercambiar mensajes entre ambas organizaciones hasta que este valor se configure como **True**.

    - **EnabledSharedAddressSpace** indica si el proveedor de hospedaje se está usando en un escenario de espacio de direcciones SIP compartido (dominio dividido).

    - **HostsOCSUsers** indica si el proveedor de hospedaje se usa para hospedar cuentas de Skype Empresarial Server. Si es **False**, el proveedor hospeda otros tipos de cuenta como, por ejemplo, cuentas de Microsoft Exchange.

    - **IsLocal** indica si el servidor proxy usado por el proveedor de hospedaje está incluido en la topología de Skype Empresarial Server.

    Para obtener más información sobre el uso de este cmdlet, vea [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Configuración del acceso de usuario para la federación con un cliente de Skype Empresarial Online

Para que todos los usuarios de su organización puedan comunicarse con socios federados, debe configurar sus cuentas de usuario. Esta configuración se aplica a todos los asociados federados, incluidos los dominios de cliente de Microsoft Skype Empresarial Online con los que se admite la federación. Para obtener más información sobre cómo configurar la compatibilidad con la federación para cuentas de usuario, consulte [Configurar directivas para controlar el acceso de usuarios federados](../external-access-policies/configure-policies-to-control-federated-user-access.md) y [Asignación de una directiva de acceso de usuario externo a un usuario habilitado para Skype Empresarial](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Compruebe las comunicaciones con un cliente de Skype Empresarial Online en Skype Empresarial Server

Para permitir que Skype Empresarial usuarios de su organización se comuniquen con los usuarios de un cliente de Skype Empresarial Online, debe haber completado los pasos siguientes:

- Reunir todos los requisitos previos. Este paso incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con federación para la organización, y configurar cuentas de usuario. Para obtener más información, consulte [Requisitos previos para federar con un cliente de Skype Empresarial Online](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
- Configurar compatibilidad con acceso a dominio en la implementación interna. Esto incluye la creación de una entrada del proveedor de hosts y la configuración de la implementación para permitir el acceso desde el dominio del cliente de Skype Empresarial Online. Para obtener más información, consulte [Configuración de la compatibilidad con la federación para un dominio de Skype Empresarial Online](#configure-federation-support-for-a-skype-for-business-online-domain).
- Configurar sus cuentas de usuario para admitir federación. Para obtener más información, consulte [Configuración del acceso de usuario para la federación con un cliente de Skype Empresarial Online](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Después de completar todos estos pasos y el administrador del cliente de Skype Empresarial Online completa toda la configuración de sus servicios en línea para admitir la federación con su organización, compruebe las comunicaciones mediante la prueba de las comunicaciones entre un usuario interno de su organización y un usuario de la Skype Empresarial  Cliente en línea. Si la comunicación no se realiza correctamente, use la herramienta de registro del servidor perimetral para capturar archivos de registro y seguimiento con el fin de solucionar el problema.
