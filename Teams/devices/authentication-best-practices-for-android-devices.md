---
title: Procedimientos recomendados de autenticación Microsoft Teams administración de dispositivos compartidos de dispositivos Android.
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Procedimientos recomendados sobre la administración de dispositivos Android compartidos en Teams. Esto incluye acceso condicional, directiva de contraseñas, consejos de autenticación multifactor y mucho más.
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
ms.openlocfilehash: 070c662c09d8b8159dbce850501026f67dabb203
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279238"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Procedimientos recomendados de autenticación Teams administración de dispositivos compartidos en dispositivos Android

Los objetivos de los dispositivos que se usan Teams diferentes estrategias de administración de dispositivos son necesarios. Por ejemplo, una tableta profesional personal usada por un único vendedor tiene un conjunto diferente de necesidades de un teléfono de llamada compartido por muchas personas de servicio al cliente.

Los administradores de seguridad y los equipos de operaciones deben planear los dispositivos que se pueden usar en la organización. Deben implementar *medidas de seguridad* que se adapten mejor a cada propósito. Las recomendaciones de este artículo facilitan algunas de esas decisiones.

>[!NOTE]
>El acceso condicional requiere una Azure Active Directory (Azure AD) Premium suscripción.

>[!NOTE]
>Es posible que las directivas para dispositivos móviles Android no se apliquen Teams dispositivos Android.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>Las recomendaciones de autenticación son diferentes para dispositivos Android personales o compartidos

Los Teams compartidos no pueden usar los mismos requisitos para la inscripción y el cumplimiento que se usan en dispositivos personales. La aplicación de requisitos de autenticación de dispositivos personales a dispositivos compartidos causará problemas de inicio de sesión.

1.  **Los dispositivos se han iniciado sesión debido a las directivas de contraseña.**

Las cuentas usadas en Teams dispositivos tienen una directiva de expiración de contraseña. Las cuentas que se usan con dispositivos compartidos no tienen un usuario específico para actualizarlas y restaurarlas a un estado de trabajo cuando expiran sus contraseñas. Si su organización requiere que las contraseñas expiren y restablezcan ocasionalmente, estas cuentas dejarán de funcionar en dispositivos Teams hasta que un administrador de Teams restablezca la contraseña e inicia sesión de nuevo.

**Reto**: Cuando se trata de acceder. Teams desde un dispositivo, la cuenta de una persona tiene una directiva de expiración de contraseña. Cuando la contraseña va a expirar, simplemente la cambian. Sin embargo, es posible que las cuentas usadas en *dispositivos* compartidos (cuentas de recursos) no estén conectadas a una sola persona que pueda cambiar una contraseña según sea necesario. Esto significa que una contraseña puede expirar y dejar a los trabajadores en el lugar, sin saber cómo reanudar su trabajo.

Cuando su organización requiera un restablecimiento de contraseña o exija la expiración de la contraseña, asegúrese de que un administrador de Teams esté preparado para restablecer la contraseña para que estas cuentas compartidas puedan volver a iniciar sesión.

2.  **Los dispositivos no pueden iniciar sesión debido a directivas de acceso condicional.**

**Reto**: Los dispositivos compartidos no pueden cumplir Azure AD directivas de acceso condicional para cuentas de usuario o dispositivos personales. Si los dispositivos compartidos se agrupan con cuentas de usuario o dispositivos personales para una directiva de acceso condicional, se producirá un error en el *inicio de sesión*.

Por ejemplo, si se requiere autenticación multifactor para acceder a Teams, se necesita la entrada de usuario de un código para completar esa autenticación. Los dispositivos compartidos no suelen tener un solo usuario que pueda configurar y completar la autenticación multifactor. Además, si la cuenta debe volver a autenticarse cada X días, un dispositivo compartido no puede resolver el reto sin la intervención de un usuario.

La autenticación multifactor no es compatible con dispositivos compartidos. Los métodos que se usarán en su lugar se describen a continuación.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Procedimientos recomendados para la implementación de dispositivos Android compartidos con Teams

Microsoft recomienda la siguiente configuración al implementar Teams dispositivos en su organización.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Usar una cuenta de recurso y reducir la expiración de la contraseña**

Teams dispositivos compartidos deben usar un [buzón de Exchange de recursos.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) La creación de estos buzones genera una cuenta automáticamente. Estas cuentas se pueden sincronizar con Azure AD desde Active Directory o crearse directamente en Azure AD. Las directivas de expiración de contraseñas para los usuarios también se aplicarán Teams las cuentas usadas en dispositivos compartidos, por lo que, para evitar interrupciones causadas por las directivas de expiración de contraseñas, establezca la directiva de expiración de contraseñas para los dispositivos compartidos para que nunca expiren.

A partir de Teams dispositivos CY21 [Actualización #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versión 1449/1.0.94.2021022403 para teléfonos Teams) y [CY2021 Actualización #2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versión 1449/1.0.96.2021051904 para Salas de Microsoft Teams en Android), los administradores de inquilinos pueden iniciar sesión en Teams dispositivos de forma remota. En lugar de compartir contraseñas con técnicos para configurar dispositivos, los administradores de inquilinos deben usar el inicio de sesión remoto para emitir códigos de verificación. Puede iniciar sesión para estos dispositivos desde el Teams de administración.

Para obtener más información, vea [Aprovisionamiento remoto e inicio de sesión para Teams dispositivos Android](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Revisar estas directivas de acceso condicional**

Azure AD acceso condicional establece requisitos adicionales que los dispositivos deben cumplir para iniciar sesión. Para Teams dispositivos, revise las instrucciones siguientes para determinar si ha sido el autor de las directivas que permitirán a los usuarios de dispositivos compartidos realizar su trabajo.

> [!TIP]
> Para obtener información general sobre el acceso condicional, vea [¿Qué es el acceso condicional](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>No usar la autenticación multifactor para dispositivos compartidos

Las cuentas de dispositivos compartidos están vinculadas a un salón o espacio físico, en lugar de a una cuenta de usuario final. Como los dispositivos compartidos no admiten la autenticación multifactor, excluya los dispositivos compartidos de las directivas de autenticación multifactor.

>[!TIP]
>Use una [ubicación con nombre o](/azure/active-directory/conditional-access/location-condition) [requiera un dispositivo compatible para](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) proteger los dispositivos compartidos.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Puede usar el acceso basado en la ubicación con ubicaciones con nombre

Si los dispositivos compartidos se aprovisionan en una ubicación bien definida que se puede identificar con un rango de direcciones IP, puede configurar el acceso condicional [](/azure/active-directory/conditional-access/location-condition) con ubicaciones con nombre para estos dispositivos. Este condicional permitirá que estos dispositivos accedan a sus recursos corporativos solo cuando estén dentro de su red.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Cuándo y cuándo no se requieren dispositivos compartidos compatibles

>[!NOTE]
>El cumplimiento del dispositivo requiere una licencia de Intune.

Si va a inscribir dispositivos compartidos en Intune, puede configurar el cumplimiento de dispositivos como un control en Acceso condicional para que solo los dispositivos compatibles puedan obtener acceso a sus recursos corporativos. Teams dispositivos se pueden configurar para directivas de acceso condicional en función del cumplimiento del dispositivo. Para obtener más información, vea [Acceso condicional: Requerir dispositivos Azure AD compatibles o híbridos](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Para establecer la configuración de cumplimiento para sus dispositivos con Intune, vea Usar directivas de cumplimiento para establecer reglas para los dispositivos [que administra con Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Los dispositivos compartidos que se usan *para el escritorio en* caliente deben excluirse de las directivas de cumplimiento. Las directivas de cumplimiento impiden que los dispositivos se inscriban en la cuenta de usuario de hot desk. **En su lugar, use ubicaciones con nombre para proteger estos dispositivos**.
> Para aumentar la seguridad, también puede requerir autenticación [multifactor](/azure/active-directory/authentication/tutorial-enable-azure-mfa) para usuarios /cuentas de usuario de hot *desking* , además de las directivas de ubicación con nombre.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Excluir dispositivos compartidos de las condiciones de frecuencia de inicio de sesión

En Acceso condicional, puede configurar la frecuencia de inicio de sesión [para](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) requerir que los usuarios vuelvan a iniciar sesión para obtener acceso a un recurso después de un período de tiempo especificado. Si se exige la frecuencia de inicio de sesión para las cuentas de salón, los dispositivos compartidos cerrarán sesión hasta que un administrador vuelva a iniciar sesión. Microsoft recomienda excluir los dispositivos compartidos de las directivas de frecuencia de inicio de sesión.

### <a name="using-filters-for-devices"></a>Usar filtros para dispositivos

[Filtros para dispositivos](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) es una característica de Acceso condicional que le permite configurar directivas más granulares para dispositivos en función de las propiedades de dispositivo disponibles en Azure AD. También puede usar sus propios valores personalizados estableciendo los atributos de extensión de 1 a 15 en el objeto de dispositivo y, a continuación, usando esos.

Use filtros para dispositivos para identificar los dispositivos de área común y habilitar directivas en dos escenarios clave:

1.  Excluir los dispositivos compartidos de las directivas aplicadas a dispositivos personales. Por ejemplo, exigir el cumplimiento del  dispositivo no se exige para los dispositivos compartidos que se usan para el  escritorio en caliente, sino que se exige para todos los demás dispositivos, en función del número de modelo.

2.  Aplicar directivas especiales en dispositivos compartidos *que no se* deben aplicar a dispositivos personales. Por ejemplo, requerir ubicaciones con nombre como directiva solo para dispositivos de área común en función de un atributo de extensión que establezca para estos dispositivos (por ejemplo: "CommonAreaPhone").

>[!NOTE] 
> Algunos atributos como **modelo**, **fabricante** y **operativoSystemVersion** solo se pueden establecer cuando Intune administra los dispositivos. Si Intune no administra los dispositivos, use atributos de extensión.
