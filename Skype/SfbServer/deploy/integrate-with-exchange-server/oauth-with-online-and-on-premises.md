---
title: Integración entre Skype empresarial online y Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuración de la autenticación de OAuth entre Exchange local y Skype empresarial online habilita las características de integración de Skype empresarial e Exchange descritas en compatibilidad de características.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278129"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Configurar la integración entre Skype empresarial online o Microsoft Teams y Exchange Server 

La configuración de la integración entre Exchange Server y Skype empresarial online habilita las características de integración de Skype empresarial e Exchange descritas en [compatibilidad de características](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tema se aplica a la integración con Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para finalizar esta tarea: 15 minutos

-  Necesita tener permisos asignados antes de poder realizar los siguientes procedimientos. Para ver qué permisos necesita, consulte el tema [Exchange and Shell Infrastructure](https://go.microsoft.com/fwlink/p/?LinkId=746511) Permissions.

- Para obtener información sobre los métodos abreviados de teclado que pueden aplicarse a los procedimientos de este tema, consulte [métodos abreviados de teclado en el centro de administración de Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar la integración entre Exchange Server y O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Paso 1: configurar la autenticación de OAuth entre Exchange Server y O365

Siga los pasos que se indican en el artículo siguiente:

[Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Paso 2: crear una cuenta de usuario de correo electrónico para la aplicación de socios de Skype empresarial online o Teams

Este paso se realiza en el servidor de Exchange. Creará un usuario de correo y le asignará los derechos de roles de administración apropiados. Esta cuenta se usará en el siguiente paso.

Especifique un dominio verificado para la organización de Exchange. Este dominio debe ser el mismo dominio usado como el dominio SMTP principal usado para las cuentas de Exchange locales. Este dominio se denomina \<dominio\> verificado en el siguiente procedimiento. Además, el \<DomainControllerFQDN\> debe ser el FQDN de un controlador de dominio.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Paso 3: crear y habilitar una aplicación de socio para Skype empresarial online o Teams

Cree una aplicación de socio y use la cuenta que acaba de crear. Ejecute el siguiente comando en el PowerShell de Exchange de su organización de Exchange local.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Comprobar que realizó todo correctamente

Verifique que la configuración sea correcta verificando que algunas de las características funcionen correctamente. 

1. Confirmar la delegación de calendarios de Outlook funciona betweeen dos usuarios de Teams con Exchange Server 2016 o 2019 buzones.

2. Confirmar el historial de conversaciones para clientes móviles está visible en la carpeta Historial de conversaciones de Outlook.

Como alternativa, mire el tráfico. El tráfico en un protocolo de enlace de OAuth es realmente distintivo (y no se parece a la autenticación básica), en particular en relación con territorios, donde comenzará a ver el tráfico de emisor que tiene el siguiente aspecto: 00000004-0000-0ff1-ce00-000000000000 @ (a veces con un/antes el signo @), en los tokens que se están transmitiendo. No verá un nombre de usuario o una contraseña, que es el punto de OAuth. Pero verá el emisor ' Office ' (en este caso, ' 4 ' es Skype empresarial) y el territorio de su plan.

Si quiere asegurarse de que está usando OAuth correctamente, asegúrese de que sabe qué esperar y sepa qué aspecto tiene el tráfico. Esto [es lo que debe esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aquí tiene un ejemplo muy estándar [de tráfico de OAuth en una aplicación de Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (lo que es realmente útil leer, aunque no usa tokens de actualización) y hay extensiones de Fiddler que le permitirán consultar su JWT de OAuth (JSON). Token Web).

Este es un [ejemplo de configuración de una](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), pero puede usar cualquier herramienta de seguimiento de red que desee para realizar este proceso.

## <a name="related-topics"></a>Temas relacionados

[Configurar la autenticación de OAuth entre organizaciones de Exchange y Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
