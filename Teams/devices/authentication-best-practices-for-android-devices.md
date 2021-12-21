---
title: Procedimientos recomendados de autenticación para dispositivos Android
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Una guía de procedimientos recomendados para Teams autenticación de dispositivos Android.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ffa30efd7f122b6d95c4545dd2d2517f3669472
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2021
ms.locfileid: "61576170"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Procedimientos recomendados de autenticación Teams dispositivos Android

En este artículo se proporcionan instrucciones generales y procedimientos recomendados para implementar directivas de autenticación para Teams teléfonos y dispositivos de llamadas.

>[!NOTE]
>El acceso condicional requiere una Azure Active Directory (Azure AD) Premium suscripción.

>[!NOTE]
>Es posible que las directivas para dispositivos móviles Android no se apliquen Teams dispositivos Android.


## <a name="personal-and-shared-devices"></a>Dispositivos personales y compartidos

Los Teams compartidos, como los dispositivos de salas de reuniones o los teléfonos de área común, no pueden usar los mismos requisitos para la inscripción y el cumplimiento que normalmente se aplican a los dispositivos personales. La aplicación de requisitos de autenticación de dispositivos personales a dispositivos compartidos causará los siguientes problemas de inicio de sesión:

1.  **Los dispositivos se han iniciado sesión debido a directivas de contraseña**

Las cuentas usadas en Teams dispositivos tienen una directiva de expiración de contraseña. A diferencia de los usuarios, las cuentas que se usan con dispositivos compartidos no tienen un usuario designado para actualizarlas y restaurarlas a un estado válido cuando expiran sus contraseñas. Si su organización requiere que las contraseñas expiren y se restablezcan periódicamente, estas cuentas dejarán de funcionar en los dispositivos Teams hasta que un administrador de Teams restablezca la contraseña e inicia sesión de nuevo.

2.  **Los dispositivos no pueden iniciar sesión debido a directivas de acceso condicional**

Los dispositivos compartidos no pueden cumplir las Azure AD de acceso condicional para cuentas de usuario o dispositivos personales. Si los dispositivos compartidos se agrupan con cuentas de usuario o dispositivos personales para una directiva de acceso condicional, se producirá un error en el inicio de sesión.

Por ejemplo, si se requiere autenticación multifactor para acceder a Teams, se requiere la intervención del usuario para completar la autenticación. Los dispositivos compartidos no admiten la autenticación multifactor. De forma similar, si la cuenta está configurada para volver a autenticar cada X días, un dispositivo compartido no puede resolver el reto sin la intervención del usuario.

## <a name="best-practices-for-teams-shared-device-deployments"></a>Procedimientos recomendados para Teams de dispositivos compartidos

Microsoft recomienda la siguiente configuración al implementar Teams dispositivos en su organización.

### <a name="password-policy"></a>**Directiva de contraseñas**

Teams dispositivos compartidos deben usar [una Exchange de recursos](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). Estas cuentas se pueden sincronizar desde Active Directory o crearse directamente en Azure AD. Las directivas de expiración de contraseñas para los usuarios también se aplican a las cuentas que se usan Teams dispositivos compartidos.

Para evitar interrupciones causadas por las directivas de expiración de contraseñas, establezca la directiva de expiración de contraseñas para dispositivos compartidos para que nunca expiren.

A partir de Teams dispositivos CY21 [Actualización #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (versión Teams 1449/1.0.94.2021022403 para teléfonos Teams) y actualización [de CY2021 #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versión 1449/1.0.96.2021051904 para Salas de Microsoft Teams en Android), los administradores de inquilinos pueden iniciar sesión en Teams dispositivos de forma remota. No comparta contraseñas con técnicos para configurar dispositivos. Un administrador, use el inicio de sesión remoto para emitir códigos de verificación y, a continuación, inicie sesión en estos dispositivos desde Teams centro de administración.

Para obtener más información, vea [Aprovisionamiento remoto e iniciar sesión para Teams dispositivos Android.](/MicrosoftTeams/devices/remote-provision-remote-login) 

### <a name="conditional-access-policies"></a>**Directivas de acceso condicional**

Azure AD acceso condicional establece requisitos adicionales que los dispositivos deben cumplir para iniciar sesión. Para Teams dispositivos, revise las siguientes instrucciones para determinar si ha sido el autor de las directivas adecuadas. Para obtener información general sobre el acceso condicional, vea [Qué es el acceso condicional.](/azure/active-directory/conditional-access/overview)

### <a name="multi-factor-authentication"></a>Autenticación multifactor

Las cuentas de dispositivos compartidos están vinculadas a un salón o espacio físico, en lugar de a una cuenta de usuario. Como los dispositivos compartidos no admiten la autenticación multifactor, excluya los dispositivos compartidos de las directivas de autenticación multifactor.

>[!TIP]
>Use una [ubicación con nombre o](/azure/active-directory/conditional-access/location-condition) requiera un dispositivo compatible [para](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) proteger los dispositivos compartidos.

### <a name="location-based-access-with-named-locations"></a>Acceso basado en ubicaciones con ubicaciones con nombre

Si los dispositivos compartidos se aprovisionan en una ubicación bien definida que se puede [](/azure/active-directory/conditional-access/location-condition) identificar con un rango de direcciones IP, puede configurar el acceso condicional con ubicaciones con nombre para estos dispositivos. Este condicional permitirá que estos dispositivos accedan a sus recursos corporativos solo cuando estén dentro de su red.

### <a name="require-compliant-device"></a>Requerir dispositivo compatible

>[!NOTE]
>El cumplimiento del dispositivo requiere una licencia de Intune.

Si va a inscribir dispositivos compartidos en Intune, puede configurar el cumplimiento de dispositivos como un control en Acceso condicional para que solo los dispositivos compatibles puedan obtener acceso a sus recursos corporativos. Teams dispositivos se pueden configurar para directivas de acceso condicional en función del cumplimiento del dispositivo. Para obtener más información, vea Acceso condicional: Requerir un dispositivo Azure AD [compatible o híbrido.](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)

Para establecer la configuración de cumplimiento para sus dispositivos con Intune, vea Usar directivas de cumplimiento para establecer reglas para los dispositivos [que administra con Intune.](/intune/protect/device-compliance-get-started)

>[!NOTE]
> Los dispositivos compartidos que se usan para hotdesking deben excluirse de las directivas de cumplimiento. Las directivas de cumplimiento impiden que los dispositivos se inscriban en la cuenta de usuario de hot-desk. En su lugar, use ubicaciones con nombre para proteger estos dispositivos.
> Para aumentar la seguridad, también puede requerir autenticación [multifactor](/azure/active-directory/authentication/tutorial-enable-azure-mfa) para los usuarios de escritorio en caliente, además de las directivas de ubicación con nombre.

### <a name="sign-in-frequency"></a>Frecuencia de inicio de sesión

En Acceso condicional, puede configurar la frecuencia de inicio de sesión [para](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) requerir que los usuarios vuelvan a iniciar sesión para obtener acceso a un recurso después de un período de tiempo especificado. Si se exige la frecuencia de inicio de sesión para las cuentas de salón, los dispositivos compartidos cerrarán sesión hasta que un administrador vuelva a iniciar sesión. Microsoft recomienda excluir los dispositivos compartidos de las directivas de frecuencia de inicio de sesión.

### <a name="filters-for-devices"></a>Filtros para dispositivos

[Filtros para dispositivos](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) es una característica de Acceso condicional que le permite configurar directivas más granulares para dispositivos en función de las propiedades de dispositivo disponibles en Azure AD. También puede usar sus propios valores personalizados estableciendo los atributos de extensión de 1 a 15 en el objeto de dispositivo y, a continuación, usando esos.

Use filtros para dispositivos para identificar los dispositivos de área común y habilitar directivas en dos escenarios clave:

1.  Excluir los dispositivos compartidos de las directivas aplicadas a dispositivos personales. Por ejemplo, exigir el cumplimiento del dispositivo no se exige para los dispositivos compartidos que se usan para el escritorio en caliente, sino que se exige para todos los demás dispositivos en función del número de modelo.

2.  Aplicar directivas especiales en dispositivos compartidos que no se deben aplicar a dispositivos personales. Por ejemplo, requerir ubicaciones con nombre como directiva solo para dispositivos de área común en función de un atributo de extensión que establezca para estos dispositivos (por ejemplo: "CommonAreaPhone").

>[!NOTE] 
> Algunos atributos como **el modelo,** **el fabricante** y **el funcionamientoSystemVersion** solo se pueden establecer cuando Intune administra los dispositivos. Si Intune no administra los dispositivos, use atributos de extensión.