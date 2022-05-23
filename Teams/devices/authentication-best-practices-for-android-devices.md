---
title: Procedimientos recomendados de autenticación para Microsoft Teams administración de dispositivos compartidos de dispositivos Android.
author: dstrome
ms.author: dstrome
manager: serdars
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
ms.openlocfilehash: 6eef76052f662b26f946bf80839a62186c287b68
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635468"
---
# <a name="authentication-best-practices-for-teams-shared-device-management-on-android-devices"></a>Procedimientos recomendados de autenticación para Teams administración de dispositivos compartidos en dispositivos Android

Los objetivos de los dispositivos usados con Teams hacen necesarias diferentes estrategias de administración de dispositivos. Por ejemplo, una tableta personal de empresa usada por un único vendedor tiene un conjunto diferente de necesidades de un teléfono de llamada compartida por muchas personas del servicio de atención al cliente.

Los administradores de seguridad y los equipos de operaciones deben planear los dispositivos que se pueden usar en la organización. Deben implementar las medidas de *seguridad* más adecuadas para cada propósito. Las recomendaciones de este artículo facilitan algunas de estas decisiones.

>[!NOTE]
>El acceso condicional requiere una suscripción Premium de Azure Active Directory (Azure AD).

>[!NOTE]
>Es posible que las directivas de Android dispositivos móviles no se apliquen a Teams Android dispositivos.

## <a name="authentication-recommendations-are-different-for-personal-versus-shared-android-devices"></a>Las recomendaciones de autenticación son diferentes para dispositivos Android personales y compartidos

Los dispositivos de Teams compartidos no pueden usar los mismos requisitos para la inscripción y el cumplimiento que se usan en los dispositivos personales. Aplicar requisitos de autenticación de dispositivos personales a dispositivos compartidos provocará problemas de inicio de sesión.

1.  **Los dispositivos han cerrado sesión debido a las directivas de contraseñas.**

Las cuentas usadas en dispositivos Teams tienen una directiva de expiración de contraseñas. Las cuentas que se usan con dispositivos compartidos no tienen un usuario específico para actualizarlos y restaurarlos a un estado de funcionamiento cuando expiran sus contraseñas. Si su organización requiere que las contraseñas expiren y se restablezcan ocasionalmente, estas cuentas dejarán de funcionar en Teams dispositivos hasta que un administrador de Teams restablezca la contraseña y vuelva a iniciar sesión.

**Desafío**: Cuando se trata de acceder. Teams desde un dispositivo, la cuenta de una persona tiene una directiva de expiración de contraseña. Cuando la contraseña va a expirar, simplemente la cambian. Sin embargo, es posible que las cuentas que se usan en *dispositivos compartidos* (cuentas de recursos) no estén conectadas a una sola persona que pueda cambiar una contraseña según sea necesario. Esto significa que una contraseña puede expirar y dejar a los trabajadores en el lugar, sin saber cómo reanudar su trabajo.

Cuando su organización requiera un restablecimiento de contraseña o exija la expiración de la contraseña, asegúrese de que un administrador de Teams esté preparado para restablecer la contraseña para que estas cuentas compartidas puedan volver a iniciar sesión.

2.  **Los dispositivos no pueden iniciar sesión debido a las directivas de acceso condicional.**

**Desafío**: Los dispositivos compartidos no pueden cumplir con las directivas de acceso condicional de Azure AD para cuentas de usuario o dispositivos personales. Si los dispositivos compartidos se agrupan con cuentas de usuario o dispositivos personales para una directiva de acceso condicional, se *producirá un error* en el inicio de sesión.

Por ejemplo, si se requiere autenticación multifactor para acceder a Teams, se necesita que el usuario escriba un código para completar esa autenticación. Por lo general, los dispositivos compartidos no tienen un único usuario que pueda configurar y completar la autenticación multifactor. Además, si la cuenta debe volver a autenticarse cada X días, un dispositivo compartido no podrá resolver el problema sin la intervención de un usuario.

La autenticación multifactor no es compatible con dispositivos compartidos. A continuación se describen los métodos que se usarán en su lugar.

## <a name="best-practices-for-the-deployment-of-shared-android-devices-with-teams"></a>Procedimientos recomendados para la implementación de dispositivos Android compartidos con Teams

Microsoft recomienda la siguiente configuración al implementar Teams dispositivos de su organización.

### <a name="use-a-resource-account-and-curtail-its-password-expiration"></a>**Usar una cuenta de recursos y limitar la expiración de la contraseña**

Teams dispositivos compartidos deben usar un [buzón de recursos Exchange](/exchange/recipients-in-exchange-online/manage-resource-mailboxes). La creación de estos buzones genera una cuenta automáticamente. Estas cuentas se pueden sincronizar con Azure AD desde Active Directory o se pueden crear directamente en Azure AD. Las directivas de expiración de contraseñas para los usuarios también se aplicarán a las cuentas usadas en Teams dispositivos compartidos, por lo tanto, para evitar interrupciones causadas por directivas de expiración de contraseñas, establezca la directiva de expiración de contraseñas para dispositivos compartidos para que nunca expiren.

A partir de Teams dispositivos CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams versión 1449/1.0.94.2021022403 para teléfonos Teams) y [CY2021 Actualización n.º 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams versión 1449/1.0.96.2021051904 para Salas de Microsoft Teams en Android), los administradores de inquilinos pueden iniciar sesión en Teams  dispositivos de forma remota. En lugar de compartir contraseñas con técnicos para configurar dispositivos, los administradores de inquilinos deben usar el inicio de sesión remoto para emitir códigos de verificación. Puede iniciar sesión para estos dispositivos desde el centro de administración de Teams.

Para obtener más información, consulta [Aprovisionamiento remoto e inicio de sesión para dispositivos Teams Android](/MicrosoftTeams/devices/remote-provision-remote-login). 

### <a name="review-these-conditional-access-policies"></a>**Revisar estas directivas de acceso condicional**

El acceso condicional de Azure AD establece requisitos adicionales que los dispositivos deben cumplir para iniciar sesión. Para Teams dispositivos, revise las instrucciones siguientes para determinar si ha creado las directivas que permitirán a los usuarios de dispositivos compartidos realizar su trabajo.

> [!TIP]
> Para obtener información general sobre el acceso condicional, vea [¿Qué es el acceso condicional](/azure/active-directory/conditional-access/overview)?

### <a name="do-not-use-multi-factor-authentication-for-shared-devices"></a>No usar la autenticación multifactor para dispositivos compartidos

Las cuentas de dispositivos compartidos están vinculadas a una sala o a un espacio físico, en lugar de a una cuenta de usuario final. Como los dispositivos compartidos no admiten la autenticación multifactor, excluya los dispositivos compartidos de las directivas de autenticación multifactor.

>[!TIP]
>Usa una [ubicación con nombre](/azure/active-directory/conditional-access/location-condition) o [requiere un dispositivo compatible](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) para proteger los dispositivos compartidos.

### <a name="you-can-use-location-based-access-with-named-locations"></a>Puede usar el acceso basado en la ubicación con ubicaciones con nombre

Si los dispositivos compartidos se aprovisionan en una ubicación bien definida que se pueda identificar con un intervalo de direcciones IP, puede configurar el Acceso condicional mediante [ubicaciones con nombre](/azure/active-directory/conditional-access/location-condition) para estos dispositivos. Este condicional permitirá que estos dispositivos accedan a sus recursos corporativos solo cuando estén dentro de su red.

### <a name="when-and-when-not-to-require-compliant-shared-devices"></a>Cuándo y cuándo no requerir dispositivos compartidos compatibles

>[!NOTE]
>El cumplimiento del dispositivo requiere una licencia de Intune.

Si va a inscribir dispositivos compartidos en Intune, puede configurar el cumplimiento de dispositivos como un control en Acceso condicional para que solo los dispositivos compatibles puedan acceder a sus recursos corporativos. Teams dispositivos se pueden configurar para directivas de acceso condicional en función del cumplimiento del dispositivo. Para obtener más información, vea [Acceso condicional: Requerir un dispositivo unido a Azure AD híbrido o compatible](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device).

Para establecer la configuración de cumplimiento para los dispositivos con Intune, vea [Usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](/intune/protect/device-compliance-get-started).

>[!NOTE]
> Los dispositivos compartidos que se usan para *hot desking* deben excluirse de las directivas de cumplimiento. Las directivas de cumplimiento impiden que los dispositivos se inscriban en la cuenta de usuario de hot desk. **En su lugar, usa ubicaciones con nombre para proteger estos dispositivos**.
> Para aumentar la seguridad, también puede [requerir autenticación multifactor](/azure/active-directory/authentication/tutorial-enable-azure-mfa) para *usuarios de hot desking o cuentas de usuario* , además de las directivas de ubicación con nombre.

### <a name="exclude-shared-devices-from-sign-in-frequency-conditions"></a>Excluir dispositivos compartidos de las condiciones de frecuencia de inicio de sesión

En Acceso condicional, puede [configurar la frecuencia de inicio de sesión](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) para que los usuarios vuelvan a iniciar sesión para obtener acceso a un recurso después de un período de tiempo especificado. Si se aplica la frecuencia de inicio de sesión para las cuentas de sala, los dispositivos compartidos cerrarán la sesión hasta que un administrador los vuelva a iniciar. Microsoft recomienda excluir los dispositivos compartidos de las directivas de frecuencia de inicio de sesión.

### <a name="using-filters-for-devices"></a>Usar filtros para dispositivos

[Filtros para dispositivos](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) es una característica del acceso condicional que le permite configurar directivas más granulares para dispositivos en función de las propiedades de dispositivo disponibles en Azure AD. También puede usar sus propios valores personalizados estableciendo los atributos de extensión 1-15 en el objeto de dispositivo y, a continuación, los usa.

Use filtros para los dispositivos para identificar los dispositivos de área común y habilitar directivas en dos escenarios clave:

1.  Excluir los dispositivos compartidos de las directivas aplicadas para dispositivos personales. Por ejemplo, exigir el cumplimiento de los dispositivos *no se exige* para los dispositivos compartidos que se usan para el escritorio rápido, sino que *se aplica* para todos los demás dispositivos, en función del número de modelo.

2.  Aplicar directivas especiales en dispositivos compartidos que *no se deben* aplicar a dispositivos personales. Por ejemplo, requerir ubicaciones con nombre como directiva solo para dispositivos de área común en función de un atributo de extensión que establezca para estos dispositivos (por ejemplo: "CommonAreaPhone").

>[!NOTE] 
> Algunos atributos como **modelo**, **fabricante** y **operativoSystemVersion** solo se pueden establecer cuando los dispositivos se administran mediante Intune. Si los dispositivos no están administrados por Intune, usa atributos de extensión.
