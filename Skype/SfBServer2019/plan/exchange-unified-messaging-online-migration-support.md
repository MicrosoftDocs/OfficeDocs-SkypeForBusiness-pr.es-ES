---
title: Soporte de migración en línea de la mensajería unificada de Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft retirará el Exchange de mensajería unificada en línea (ExchUMO) antes del 28 de febrero de 2020. En este artículo se resume lo que los clientes afectados deben saber y hacer para planear la continuidad de su negocio.
ms.openlocfilehash: 933ba625506496c01242b26712e9b6d5b020dbb199c5f515444f7a8734fb84b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279598"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Soporte de migración en línea de la mensajería unificada de Exchange

> [!IMPORTANT]
> **El servicio de mensajería unificada en Exchange Online está fuera de soporte técnico a partir del 28 de febrero de 2020, 5 p. m., hora del Pacífico. Microsoft ha migrado todas las cuentas de correo de voz Correo de voz en la nube servicio de correo de voz. Cualquier tráfico de operador automático restante no se supervisará y podría interrumpirse en cualquier momento.**

En referencia [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) al anuncio del 8 de febrero de 2019, Microsoft retirará el servicio Exchange Unified Messaging Online (ExchUMO) antes del 28 de febrero de 2020. En este artículo se ofrece un resumen de lo que los clientes afectados deben saber y hacer para planear la continuidad de su negocio.

Los clientes implementan ExchUMO para los servicios de correo de voz, operador automático, cola de llamadas y integración de fax. Microsoft planea ayudar a los clientes a migrar a Sistema telefónico servicios que ya admiten miles de clientes en Skype Empresarial Online y Microsoft Teams.

El correo de voz es principalmente una migración controlada por Microsoft; la participación y/o la inversión de los administradores pueden ser necesarias para un subconjunto de clientes. El operador automático es una migración controlada por el administrador; deberá volver a crear los árboles de operador automático de ExchUMO existentes en el servicio de nube Operador automático nube. Los clientes que consumen cualquiera de las características de ExchUMO con una PBX de terceros no se migrarán a Skype servicios en la nube porque no admiten sistemas PBX de terceros. En este [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)se anunció un plan de retiro para la compatibilidad con terceros y los clientes de este modelo de implementación pueden migrar a sus usuarios a una de las plataformas o servicios de comunicaciones unificadas de Microsoft o adquirir una solución de correo de voz de terceros o operador automático para estos usuarios. La integración de fax no se admite en los servicios basados en la nube; los clientes tendrán que migrar a una solución de terceros.

## <a name="who-is-affected"></a>Quién está afectado?

Los clientes que usan cualquiera de las siguientes características del servicio Exchange de mensajería unificada en línea se ven afectados:

- Servicio de correo de voz
- Operador automático servicio
- Servicio de cola de llamadas
- Integración de fax

> [!Note]
> Los clientes que usan cualquiera de las Exchange Server locales con mensajería unificada no se ven afectados.

Obtenga más información sobre el impacto de la experiencia de usuario y administrador en [el impacto de la experiencia del usuario.](#user-experience-impact)

## <a name="migration-plan-overview"></a>Introducción al plan de migración

Microsoft ha identificado varias implementaciones de clientes que consumen características de ExchUMO y ayudarán a los clientes a migrar según el siguiente plan.

|Grupo de clientes |Escala de tiempo  |Detalles  |
|---------|---------|---------|
|Clientes que están listos para migrar<br><br>Características para migrar:<br><ul><li>Correo de voz</ul>   |   Marzo - Mayo de 2019  |Ejemplos:<ul><li>    Clientes con implementación y uso de correo de voz sencillos<li>Clientes que tienen todos los requisitos establecidos para que Microsoft ejecute la migración<ul>|
|Clientes con requisitos previos<br><br>Características para migrar:<br><ul><li>Correo de voz<li>Operador automático<li>Cola de llamadas</ul> |  Mayo - Diciembre de 2019 |Ejemplos: <br><ul><li>La configuración híbrida no está completa<li>Los números RTC híbridos no están configurados</ul>|
|Clientes que requieren la participación del administrador & inversión de clientes<br><br>Características para migrar:<ul><li>correo de voz<li>Operador automático<li>Colas de llamadas<li>Integración de fax</ul>| Para febrero de 2020  | Ejemplos: <br><ul><li>El servicio de ExchUMO lo consume PBX de terceros<li>Clientes con requisitos de acceso de suscriptor RTC<li>Clientes en SFB 2010 (no compatible)<li>Integración de fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Directrices de migración de correo de voz

### <a name="get-informed"></a>Informarse

Familiarícese con el [anuncio del blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) y este artículo para planear una migración sin problemas para los usuarios. Consulta [Comprobar Skype Empresarial correo de voz y opciones para](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) obtener más información sobre las Sistema telefónico correo de voz.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Establecer una topología Skype Empresarial híbrida

Si no tiene una topología híbrida Skype Empresarial, debe hacerlo para permitir una migración sin problemas de los usuarios de correo de voz. Consulte [Configurar Skype Empresarial híbrido para](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) obtener más información.

> [!Note]
> No es necesario migrar los usuarios en línea para la migración del servicio de correo de voz. Sin embargo, para que los usuarios locales aprovechen Sistema telefónico servicio de correo de voz, se debe establecer una topología híbrida.

### <a name="plan-your-auto-attendant-migration"></a>Planear la migración del operador automático

Los administradores pueden empezar a migrar sus operadores automáticos de ExchUMO al operador automático en la nube en cualquier momento. Consulta [Configurar un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant) para obtener más información.

Microsoft sigue entregando funcionalidades de operador automático adicionales que los clientes podrían considerar necesarias para su migración. Los administradores deben evaluar el conjunto de características y migrar sus instancias de operador automático en consecuencia. Para obtener una comparación de la lista de características, consulte la matriz de características de servicios basados en la nube [de ExchUMO](#exchumo-and-azure-cloud-based-services-feature-matrix)y Azure .

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planear la validación y pruebas posteriores a la migración del correo de voz

La migración del correo de voz está controlada por Microsoft. Los administradores no tienen que hacer nada, dado que se establece la topología híbrida previamente necesaria. Microsoft realiza la validación y las pruebas necesarias para asegurarse de que la migración del correo de voz de los usuarios no se interrumpe. Se recomienda a los administradores que realicen pruebas y validación de su lado. Consulta Plan de prueba sugerido y validación posterior a la migración [para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) para obtener un plan de prueba recomendado.

> [!Note]
> Lync Server 2010 no es compatible. Si está en una implementación de servidor de 2010, debe planear una actualización del servidor o considerar la posibilidad de migrar los usuarios a Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Supervisar el Centro de notificaciones de administración

Busca un aviso en el Centro de notificaciones de administración con más detalles y una escala de tiempo con respecto a la migración de los usuarios. Las notificaciones se envían al menos 30 días antes del período de migración.

> [!Note]
> Si recibió una notificación con la escala de tiempo de migración de los usuarios y desea posponer la migración por un motivo crítico para la empresa, puede hacerlo ponerse en contacto con el Soporte técnico de Microsoft. No puede posponer la migración más allá de la fecha de retiro del 28 de febrero de 2020. Para los clientes que pueden tener más preguntas, póngase en contacto con el equipo de su cuenta o con el Soporte técnico de Microsoft. Los clientes que ya Microsoft 365 o Office 365 pueden enviar un caso de soporte técnico a través del Centro de administración de Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Considere la posibilidad de participar en una migración planeada

Puedes participar en una migración de servicio de correo de voz planeada a CVM. Antes de participar, revise los detalles de este artículo, especialmente las secciones siguientes:

- Pasos de migración (esta sección)
- Matriz de características de servicios basados en la nube de ExchUMO y Azure
- Impacto de la experiencia del usuario

Al elegir una migración administrada, no recibirá una notificación previa a la migración de 30 días en el centro de mensajes del portal Microsoft 365 administración.

Para participar en una migración planeada, envíe una solicitud de correo electrónico desde la dirección de correo electrónico del administrador a [cvm@microsoft.com](mailto:cvm@microsoft.com) con la siguiente información:

- Fecha preferida (martes): las oleadas de migración se ejecutan todos los martes. Seleccione una fecha en un martes que no supere el 12/3/2019.
 
- Identificador de inquilino: número de 32 caracteres con este formato 0046728c-688a-4472-a38f-098fec60ac6x. Puede encontrar el identificador de inquilino en el portal de administración de Microsoft 365 en Azure AD o mediante el siguiente cmdlet de PowerShell:`Get-CsTenant | Select ObjectId`

Recibirá una confirmación por correo electrónico una vez que el inquilino se migre correctamente.

## <a name="auto-attendant-migration-guidelines"></a>Directrices de migración de operadores automáticos

Los administradores de la organización de Microsoft 365 y Office 365 deben volver a crear sus operadores automáticos de mensajería unificada en línea de Exchange en el servicio de Microsoft Cloud Operador automático y cambiar sus números de teléfono locales antes de la fecha de retiro del servicio UMO de Exchange del 28 de febrero de 2020. Esta es la guía recomendada para migrar y probar correctamente nuevos operadores automáticos en la nube. Si tiene un gran número de operadores automáticos, puede usar los scripts Exchange um Operador automático a [Cloud Operador automático Migration](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) para simplificar la migración masiva de operadores automáticos.

### <a name="auto-attendant-setup"></a>Configuración del operador automático

Le recomendamos encarecidamente que inicie la configuración de los nuevos operadores automáticos antes de tiempo para evitar problemas de última hora y familiarizarse con la funcionalidad y experiencia del servicio de Operador automático nube. Para los operadores automáticos que requieren una o más características de espacio, puede crear y probar los operadores automáticos cuando las características de espacio estén disponibles para prepararse para la implementación. Para obtener más información acerca de las características de [separación,](#appendix)vea el Apéndice .

1. Use el Exchange cmdlets UMO para exportar la configuración de operadores automáticos existentes mediante [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Use el cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) en Exchange Online PowerShell para exportar los archivos multimedia de saludo (si se usan) y convertirlos a .mp3 formato.
3. Siga las instrucciones de [Plan Cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) y Set up a Cloud auto attendant to create auto [attendants](/microsoftteams/create-a-phone-system-auto-attendant) by using the Microsoft Teams admin center or Powershell.
4. Revisa los saludos si cambiaron las opciones del menú.
5. Configure las transferencias a los grupos de respuesta mediante la solución alternativa "Operador automático transferencia de llamadas a RTC" en la [sección Problemas](#known-issues) conocidos de este artículo.  
6. Pruebe los nuevos operadores automáticos llamándolos internamente o asignando un número de teléfono de prueba.  

### <a name="cutover"></a>Total

1. Cambie los números de teléfono de Exchange operadores automáticos de UMO a los nuevos operadores automáticos.
2. Mueva el URI de SIP del objeto de contacto a la cuenta de recurso.
3. Pruebe y valide los operadores automáticos con los números de teléfono recién asignados.

## <a name="appendix"></a>Apéndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de características de servicios basados en la nube de ExchUMO y Azure

| Servicio | Nivel de característica | Característica | Notas  | VM/AA en la nube  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Características del servicio| PBX de terceros compatible    | Incluir todas las características proporcionadas a PBX de terceros, como MWI (indicador de mensajes en espera) mediante mensajes de notificación SIP desde Exchange UM Online | N   | v    |
| VM | Características del servicio  | Compatibilidad Skype Empresarial Server   |  | v | v    |
| VM | Características del servicio | Compatibilidad Microsoft Teams|  | v | N    |
| VM | Características del servicio | Exhibición de documentos electrónicos y retención  | Para seguridad y cumplimiento  | v | v    |
| VM | Características del servicio | Exchange Compatibilidad con reglas | Para seguridad y cumplimiento  | v | v    |
| VM | Características de usuario | Acceso telefónico local RTC  | Acceso de suscriptor  | N | v    |
| VM | Características de usuario | Delegado  | correo electrónico de llamada perdida  | N | v    |
| VM | Características de usuario | Rtc Outlook de voz   | Acceso de suscriptor  | N | v    |
| VM | Características de usuario | Acceso telefónico mediante un extremo autenticado | Llamar al servicio de correo de voz para escuchar mensajes de voz y cambiar la configuración del correo de voz| v | v    |
| VM | Características de usuario | Configuración del usuario para deshabilitar el correo de voz   |  | v | v    |
| VM | Características de usuario | Configuración del usuario para cambiar el saludo personal  |  | v | v    |
| VM | Características de usuario | Configuración del usuario para crear un saludo OOF  |  | v | v    |
| VM | Características de usuario | Configuración del usuario para cambiar el idioma predeterminado  |  | v | v    |
| VM | Características de usuario | Configuración del usuario para sobrescribir el saludo predeterminado con TTS  |  | v | N    |
| VM | Características de usuario | Grabar saludos personales (dispositivo autenticado) |  | v | v    |
| VM | Características de usuario | Grabar saludos personales (RTC): reproducir en el teléfono |  | N | v    |
| VM | Características de usuario | Configuración del usuario para deshabilitar la transcripción |  | N | v    |
| VM | Características de usuario | Transcripción  |  | v | v    |
| VM | Características de usuario | MWI (indicador de mensaje en espera) mediante mensajes de notificación SIP |  | N | v    |
| VM | Características de usuario | Formato de archivo de audio MP3 en Outlook    |  | v | v    |
| VM | Características de usuario | Control de reproducción de velocidad variable |  | v | v    |
| VM | Características de usuario | Reenviar un correo de voz  | Reenviar un correo de voz recibido a otros usuarios | v | v    |
| VM | Características de usuario | Enviar un mensaje de voz a un grupo de usuarios  |Difusión de correo de voz   | N | v   |
| VM | Características de usuario | Notificación de correo de voz mediante SMS    | Los usuarios pueden recibir un SMS cuando tienen un nuevo correo de voz    | N | v    |
| VM | Características de usuario | Idiomas de saludo compatibles | Detalles aquí: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| VM | Características de usuario | Reglas de contestador automático |  | v | v    |
| VM | Características de usuario | Reproducir en teléfono (RTC):para reproducir el mensaje | Llámeme en mi celda para escuchar el mensaje de voz  | N | v    |
| VM | Características de usuario | Reproducir en el teléfono (autenticación): para reproducir el mensaje | Llamarme en mi dispositivo autenticado  | N | v    |
| VM | Características de usuario | Buzón compartido entre varios usuarios |  | v | v    |
| VM | Características del autor de la llamada  | Experiencia del autor de la llamada: correo de voz protegido | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como protegido| N | v    |
| VM | Características del autor de la llamada  | Experiencia del autor de la llamada: correo de voz privado | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como privado  | N | v    |
| VM | Características del autor de la llamada  | Detección de silencio   |  | N | v    |
| VM | Tenant-Admin características | Correo de voz protegido de nivel de servidor    | Tenant-admin puede configurar una regla de nivel de servicio para marcar el correo de voz entrante como protegido | v | v    |
| VM | Tenant-Admin características | Cambiar el límite de tiempo de duración de la grabación  |     | v | v    |
| VM | Tenant-Admin características | Cambiar tiempo de espera de detección de silencio    |  | N/D    | v    |
| VM | Tenant-Admin características | Cambiar el número de errores de entrada | CVM: codificado de forma codificada en 3 | N | v    |
| VM | Tenant-Admin características | Cambiar el idioma predeterminado |  | v | v    |
| VM | Tenant-Admin características | Deshabilitar/habilitar la transcripción |  | v | v    |
| VM | Tenant-Admin características | Deshabilitar/habilitar la notificación de llamada perdida |  | N | v    |
| VM | Tenant-Admin características | Ayudar a Microsoft a mejorar la vista previa del correo de voz    |  | v | v    |
| VM | Tenant-Admin características | Personalizar mensaje de texto para usuarios habilitados|  | N/D    | v    |
| VM | Tenant-Admin características | Enmascaramiento de profanidad de transcripción|  | v | N    |
| VM | Tenant-Admin características | Directiva de correo de voz    |   | v | v    |
| VM | Tenant-Admin características | Administración del portal web   |  | CY19   | v    |
| VM | Tenant-Admin características | PowerShell   |  | v | v    |
| MENSAJERÍA UNIFICADA | Características de usuario | Indicador de espera de mensajes (MWI) en Skype Empresarial teléfonos certificados   |Puede ser proporcionado por un socio telefónico  | No | Sí    |
| AA | Características del servicio | PBX de terceros compatible con AA    |  | N | v    |
| AA | Características del servicio | Compatibilidad Skype Empresarial Server   |  | v | v    |
| AA | Características del servicio | Compatibilidad Microsoft Teams|  | v | N    |
| AA | Características del servicio | Marcado por nombre, entrada DTMF    |  | v | v    |
| AA | Características del servicio | Marcado por nombre, entrada de voz  |  | v | v    |
| AA | Características del servicio | Compatibilidad con varios idiomas | Detalles del idioma aquí: https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| AA | Características del servicio | Transferencia a operador, CQ o usuario |  | v | v    |
| AA | Características del servicio | Transferencia a número RTC internamente (DID RNL)  |  | v | v    |
| AA | Características del servicio | Transferir a un número RTC externamente  |  | Consulte la sección Problemas conocidos a continuación | v    |
| AA | Características del servicio | Horario comercial |  | v | v    |
| AA | Características del servicio | Opciones de menú | Opciones del menú IVR  | v | v    |
| AA | Características del servicio | Asignar un número RTC de nube a AA |  | v | N    |
| AA | Características del servicio | Asignar un número RTC local a AA  |  | v | v    |
| AA | Características del servicio | Selección de usuario personalizada  | Permitir que los autores de llamadas lleguen a una lista personalizada de usuarios de la organización| v | v    |
| AA | Características del servicio | Tratamiento de after-hours and holidays  |  | v | v    |
| AA | Características del servicio | Saludo personalizado con texto a voz  |  | v | v    |
| AA | Características del servicio | Marcado de extensión   | Llegar a un usuario marcando su extensión  | v   | v    |
| AA | Características del servicio | Buzón para que los autores de llamadas de AA dejen un mensaje    |  | v   | v    |
| AA | Características del servicio | Varias asignaciones de números RTC a un AA|  | v | v    |
| AA | Tenant-Admin características | Administración del portal web   |  | v | N    |
| AA | Tenant-Admin características | Cmdlets de PowerShell  |  | v | v    |
| Fax| Características del servicio | Integración de fax|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de prueba sugerido y validación posterior a la migración para administradores

Para validar que los usuarios se han migrado a Correo de voz en la nube, deje un correo de voz a un usuario y compruebe el cuerpo del mensaje en Outlook. Correo de voz en la nube mensajes tienen un pie de página que dice:

"Gracias por usar la transcripción. Si no ve una transcripción anterior, se debe a que la calidad de audio no era lo suficientemente clara como para transcribir".

Al probar la funcionalidad del correo de voz después de migrar los usuarios, asegúrese de tener en cuenta los siguientes escenarios:

- Valide el acceso al correo de voz en todos los tipos de punto de conexión de la organización, como aplicaciones y teléfonos IP.
- Valide con usuarios de ejemplo que los saludos personalizados configurados se reproducen en las personas que llaman.
- Si su organización tiene un requisito legal o de cumplimiento para deshabilitar la transcripción para los usuarios, asegúrese de que está deshabilitada después de la migración. Para obtener más información, vea [Configurar Correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail).
- Si ha configurado anteriormente las Exchange y las reglas de vm, asegúrese de que son eficaces.
- Familiarícese con los cmdlets de PowerShell Correo de voz en la nube servicio para cambiar la configuración del usuario.  

### <a name="user-experience-impact"></a>Impacto de la experiencia del usuario

A continuación se ofrece información general sobre la experiencia de migración del correo de voz del usuario final.


|Experiencia  |Cambio en la experiencia del usuario|
|---------|---------|
|Notificación por correo electrónico | Sin cambios<br>No se envía ningún correo electrónico a los usuarios que les notifican acerca de la activación o migración de cuentas de correo de voz. |
|Acceso a mensajes anteriores | Sin cambios<br>Los usuarios tienen acceso a sus mensajes de correo de voz anteriores en todos los puntos de conexión admitidos. |
|Recepción de vm en outlook, aplicaciones SFB| Sin cambios<br>Los usuarios siguen recibiendo sus mensajes de correo de voz en todos los puntos de conexión compatibles. |
|Transcripción | Mejorado<br>La transcripción de CVM tiene una tasa de precisión mucho mayor y los idiomas admitidos que ExchUMO. |
|Configuración de usuario | Nueva experiencia<br>Los usuarios pueden cambiar sus preferencias desde un Portal de configuración de usuario (USP). Los usuarios pueden acceder a su USP desde un hipervínculo en su correo de voz o el botón User-Settings en su cliente SFB; https://aka.ms/vmsettings.
 |Características| Consulte la comparación del conjunto de características para obtener más información. |
|Outlook reglas para mensajes de vm | Sin cambios<br>Las reglas creadas anteriormente se aplicarán a los mensajes CVM después de la migración.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Administración de usuarios y aprovisionamiento en CVM

Los Skype Empresarial nuevos se aprovisionarán automáticamente para el correo de voz en la nube cuando se cree. No se requiere ninguna licencia o trabajo de administrador adicional para aprovisionar nuevos usuarios de correo de voz. Consulte [Configurar Correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail) información sobre la administración de directivas para usuarios existentes y nuevos.

### <a name="admin-auto-attendant-management-experience"></a>Experiencia de administración Operador automático administración

Para obtener más información acerca de los operadores automáticos, consulte [Configurar un operador automático en la nube.](/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>Problemas conocidos

#### <a name="greeting-inconsistencies"></a>Incoherencias de saludo

El acceso de suscriptor puede seguir funcionando para el inquilino hasta que el servicio se retire por completo, incluso después de que todos los usuarios se hayan migrado a Correo de voz en la nube. Para evitar la confusión del usuario y una experiencia incoherente, deshabilite el acceso de suscriptor ya que los saludos cambian después de la migración. Para ello, quite el contacto exum para cada línea de acceso de suscriptor mediante `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Operador automático de llamadas a RTC

Para transferir una llamada de operador automático a un número de teléfono RTC externo mediante Skype Empresarial Server o un servicio de grupo de respuesta (RGS) en Skype Empresarial Server, cree un nuevo usuario local con el reenvío de llamadas establecido en el número de teléfono RTC o número de teléfono RGS. El usuario debe estar habilitado y configurado correctamente para Telefonía IP empresarial y tener asignada una directiva de voz.

#### <a name="shared-mailbox-is-still-accessible"></a>El buzón compartido sigue siendo accesible

Un buzón compartido configurado mediante Exchange UM Online sigue recibiendo mensajes después de la migración a CVM y se puede acceder a los usuarios a través de Outlook. Sin embargo, el acceso para cambiar los mensajes de saludo de estos buzones no estará disponible una vez migrados a CVM. Los clientes con buzones compartidos que se usan para capturar autores de llamadas de operadores automáticos deben aprovechar las capacidades de buzones compartidos de operadores automáticos y colas de llamadas una vez publicados (ETA octubre de 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Se muestra el banner "Username is not using Skype Empresarial"

El servicio CVM se basa en la infraestructura Microsoft Teams y las llamadas de un cliente de Skype Empresarial pueden hacer que se muestre un banner de información en el cliente que dice: "Username no usa Skype Empresarial. Para una experiencia más completa, cambie a Teams o inicie una Skype reunión".
Asegúrese de actualizar el cliente de Skype Empresarial usuarios a la última actualización de cliente C2R para evitar que aparezca este banner.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurar correo de voz" le lleva a OWA

Al  hacer clic en Configurar correo de voz desde el cliente, seguirá llevando Skype Empresarial Server clientes de 2015/2013 a la página del portal de Office Web Access (OWA) después de la migración a CVM. Se han quitado todas las opciones de configuración de la pestaña Correo de voz de OWA y se mostrará un banner con un vínculo de redireccionamiento para llevar a los usuarios al portal de configuración de usuario de CVM.

#### <a name="changing-greeting-remotely"></a>Cambiar el saludo de forma remota

El acceso de suscriptor RTC no se admite en CVM. Para los usuarios que necesitan cambiar su saludo de forma remota, se ha agregado una opción de menú "Cambiar el saludo" al servicio IVR de correo de voz para clientes móviles. Los usuarios pueden llamar a este servicio presionando y manteniendo presionada la tecla "1" en el panel de marcado del cliente móvil.