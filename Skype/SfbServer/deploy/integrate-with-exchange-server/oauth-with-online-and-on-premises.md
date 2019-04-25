---
title: Integración entre Skype para profesionales Online y Exchange server
ms.reviewer: cbland
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configuración de OAuth autenticación entre Exchange local y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en compatibilidad con la característica.
ms.openlocfilehash: 976aae8287c1d9f209975d53ebc64ac80033c591
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216665"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Configurar la integración entre Skype para la empresa en línea o los equipos de Microsoft y Exchange Server 

Configuración de la integración entre Exchange server y Skype para profesionales en línea permite la Skype para características empresariales y de integración de Exchange que se describen en [función de soporte técnico](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

En este tema se aplica a la integración con Exchange Server 2013 a través de 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para finalizar esta tarea: 15 minutos

-  Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos. Para ver qué permisos necesita, vea el tema de [permisos de infraestructura de Exchange y el Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Para obtener información sobre los métodos abreviados de teclado que se pueden aplicar a los procedimientos descritos en este tema, vea [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar la integración entre Exchange Server y Office 365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Paso 1: Configurar la autenticación de OAuth entre Exchange Server y Office 365

Realice los pasos en el siguiente artículo:

[Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Paso 2: Crear una nueva cuenta de usuario de correo para la Skype para profesionales en línea o de la aplicación de socio de equipos

En este paso se realiza en el servidor de Exchange. Creará un usuario de correo y le asignará los derechos de roles de administración apropiados. Esta cuenta se usará en el siguiente paso.

Especifique un dominio comprobado para la organización de Exchange. Este dominio debe ser el mismo dominio que se utiliza como el dominio SMTP principal que se utiliza para las cuentas de Exchange local. Este dominio se conoce como \<su dominio comprobado\> en el siguiente procedimiento. Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Este comando ocultará al nuevo usuario de correo de las listas de direcciones.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Los dos comandos siguientes asignarán los roles de administración UserApplication y ArchiveApplication a esta nueva cuenta.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Paso 3: Crear y habilitar una aplicación de socio de Skype para profesionales en línea o equipos

Cree una aplicación de socio y use la cuenta que acaba de crear. Ejecute el siguiente comando en Exchange PowerShell en sus instalaciones de organización de Exchange.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Comprobar que realizó todo correctamente

Compruebe que la configuración es correcta mediante la comprobación de que algunas de las características funcionan correctamente. 

1. Confirmar la delegación de calendario de Outlook funciona comprendido entre dos usuarios de los equipos con Exchange Server 2016 o buzones 2019.

2. Confirme el historial de conversaciones para clientes móviles está visible en la carpeta Historial de conversaciones de Outlook.

Como alternativa, examine el tráfico. El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no el aspecto de la autenticación básica), especialmente alrededor de dominios, donde podrá comenzar a ver el tráfico de emisor que tiene este aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con una / antes de el signo @), en los tokens que se pasan. No podrá ver un nombre de usuario o contraseña, que es el punto de OAuth. Pero se verá al emisor 'Office': en este caso '4' es Skype para empresas – y el dominio Kerberos de su suscripción.

Si desea estar seguro de que ya está utilizando OAuth, asegúrese de que saber qué esperar y saber lo que el tráfico debe ser similar. Es así [aquí es qué esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí es bastante estándar de [ejemplo de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente útil para leer, aunque no utilice tokens de actualización) y hay extensiones de Fiddler que le permiten buscar en su OAuth JWT (JSON Token de Web).

Este es un [ejemplo de configuración de una copia de seguridad](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero se puede usar cualquier herramienta de seguimiento de red que desee para llevar a cabo este proceso.

## <a name="related-topics"></a>Temas relacionados

[Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
