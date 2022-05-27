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
ms.localizationpriority: medium
description: Microsoft retirará el servicio Exchange Unified Messaging Online (ExchUMO) antes del 28 de febrero de 2020. En este artículo se resume lo que los clientes afectados deben saber y hacer para planear su continuidad empresarial.
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676372"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Soporte de migración en línea de la mensajería unificada de Exchange

> [!IMPORTANT]
> **El servicio de mensajería unificada de Exchange Online no es compatible a partir del 28 de febrero de 2020, hora del Pacífico a las 5 p. m. Microsoft ha migrado todas las cuentas de correo de voz a Correo de voz en la nube servicio. Cualquier tráfico de operador automático restante no se supervisará y podría interrumpirse en cualquier momento.**

En referencia al [anuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) del 8 de febrero de 2019, Microsoft retirará el servicio Exchange Unified Messaging Online (ExchUMO) antes del 28 de febrero de 2020. En este artículo se ofrece un resumen de lo que los clientes afectados deben saber y hacer para planear su continuidad empresarial.

ExchUMO lo implementan los clientes para el correo de voz, el operador automático, la cola de llamadas y los servicios de integración de fax. Microsoft planea ayudar a los clientes a migrar a servicios de Sistema telefónico que ya admiten miles de clientes en Skype Empresarial Online y Microsoft Teams.

El correo de voz es principalmente una migración controlada por Microsoft; la participación del administrador o la inversión podrían ser necesarias para un subconjunto de clientes. El operador automático es una migración controlada por el administrador; tendrá que volver a crear los árboles de operador automático de ExchUMO existentes en el servicio en la nube operador automático en la nube. Los clientes que consumen cualquiera de las características de ExchUMO con una PBX de terceros no se migrarán a Skype servicios en la nube porque no admiten sistemas PBX de terceros. En [este blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853) se anunció un plan de retirada para el soporte técnico de terceros, y los clientes de este modelo de implementación pueden migrar sus usuarios a una de las plataformas o servicios de comunicaciones unificadas de Microsoft o adquirir un correo de voz de terceros o una solución de operador automático para estos usuarios. La integración de fax no se admite en los servicios basados en la nube; los clientes tendrán que migrar a una solución de terceros.

## <a name="who-is-affected"></a>Quién se ve afectado?

Los clientes que usan cualquiera de las siguientes características del Exchange servicio unified messaging online se ven afectados:

- Servicio de correo de voz
- Servicio de operador automático
- Servicio de cola de llamadas
- Integración de fax

> [!Note]
> Los clientes que usan cualquiera de los Exchange Server locales con mensajería unificada no se ven afectados.

Obtenga más información sobre el impacto de la experiencia de usuario y administrador en [el impacto de la experiencia del usuario](#user-experience-impact).

## <a name="migration-plan-overview"></a>Introducción al plan de migración

Microsoft ha identificado varias implementaciones de clientes que consumen características de ExchUMO y que ayudarán a los clientes a migrar en función del siguiente plan.

|Grupo de clientes |Escala de tiempo  |Detalles  |
|---------|---------|---------|
|Clientes que están listos para migrar<br><br>Características que se van a migrar:<br><ul><li>Correo de voz</ul>   |   Marzo : mayo de 2019  |Ejemplos:<ul><li>    Clientes con implementación y uso sencillos del correo de voz<li>Clientes que tienen todos los requisitos establecidos para que Microsoft ejecute la migración<ul>|
|Clientes con requisitos previos<br><br>Características que se van a migrar:<br><ul><li>Correo de voz<li>Operador automático<li>Cola de llamadas</ul> |  Mayo : diciembre de 2019 |Ejemplos: <br><ul><li>La configuración híbrida no está completa<li>Los números RTC híbridos no están configurados</ul>|
|Clientes que requieren la participación del administrador & la inversión del cliente<br><br>Características que se van a migrar:<ul><li>correo de voz<li>Operador automático<li>Colas de llamadas<li>Integración de fax</ul>| Para febrero de 2020  | Ejemplos: <br><ul><li>El servicio ExchUMO lo consume pbx de terceros<li>Clientes con requisitos de acceso de suscriptor RTC<li>Clientes en SFB 2010 (no compatible)<li>Integración de fax</ul> |

## <a name="voicemail-migration-guidelines"></a>Directrices de migración del correo de voz

### <a name="get-informed"></a>Obtener información

Familiarícese con el [anuncio del blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) y este artículo para planear una migración sin problemas para los usuarios. Consulta [Comprobar Skype Empresarial correo de voz y opciones](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obtener más información sobre las funcionalidades de correo de voz de Sistema telefónico.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Establecimiento de una topología híbrida Skype Empresarial

Si no tiene establecida una topología híbrida Skype Empresarial, debe hacerlo para habilitar una migración sin problemas de los usuarios del correo de voz. Consulte [Configuración de Skype Empresarial híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obtener más información.

> [!Note]
> No es necesario migrar los usuarios en línea para la migración del servicio de correo de voz. Sin embargo, para que los usuarios locales aprovechen Sistema telefónico servicio de correo de voz, se debe establecer una topología híbrida.

### <a name="plan-your-auto-attendant-migration"></a>Planear la migración del operador automático

Los administradores pueden empezar a migrar sus operadores automáticos de ExchUMO al operador automático en la nube en cualquier momento. Consulte [Configuración de un operador automático](/microsoftteams/create-a-phone-system-auto-attendant) en la nube para obtener más información.

Microsoft sigue ofreciendo funcionalidades de operador automático adicionales que los clientes podrían considerar necesarias para su migración. Los administradores deben evaluar el conjunto de características y migrar sus instancias de operador automático en consecuencia. Para ver una comparación de la lista de características, consulte la [matriz de características de servicios basados en la nube de ExchUMO y Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planear la validación y las pruebas posteriores a la migración del correo de voz

La migración del correo de voz está controlada por Microsoft. No es necesario que los administradores hagan nada, dado que se establece la topología híbrida de requisitos previos. Microsoft realiza la validación y las pruebas necesarias para asegurarse de que la migración del correo de voz de los usuarios no se interrumpe. Se recomienda a los administradores que realicen pruebas y validación de su lado. Consulte [Plan de pruebas sugerido y validación posterior a la migración para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) para obtener un plan de prueba recomendado.

> [!Note]
> Lync Server 2010 no es compatible. Si está en una implementación de servidor de 2010, debe planear una actualización del servidor o considerar la posibilidad de migrar los usuarios a Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Supervisión del Centro de notificaciones de Administración

Vea un aviso en el Centro de notificaciones de Administración con más detalles y una escala de tiempo con respecto a la migración de los usuarios. Las notificaciones se envían al menos 30 días antes del período de migración.

> [!Note]
> Si ha recibido una notificación con la escala de tiempo de migración de los usuarios y desea posponer la migración por una razón crítica para la empresa, puede hacerlo poniéndose en contacto con Soporte técnico de Microsoft. No puede posponer la migración más allá de la fecha de retirada del 28 de febrero de 2020. Para los clientes que puedan tener más preguntas, póngase en contacto con el equipo de su cuenta o Soporte técnico de Microsoft. Los clientes que ya usan Microsoft 365 o Office 365 pueden enviar un caso de soporte técnico a través de la Centro de administración de Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Considere la posibilidad de participar en una migración planeada

Puede optar por una migración planeada del servicio de correo de voz a CVM. Antes de participar, revise los detalles de este artículo, especialmente las secciones siguientes:

- Pasos de migración (esta sección)
- Matriz de características de servicios basados en la nube de ExchUMO y Azure
- Impacto en la experiencia del usuario

Al elegir una migración administrada, no recibirá una notificación previa a la migración de 30 días en el centro de mensajes del portal de administración de Microsoft 365.

Para participar en una migración planeada, envíe una solicitud de correo electrónico desde la dirección de correo electrónico del administrador a [cvm@microsoft.com](mailto:cvm@microsoft.com) con la siguiente información:

- Fecha preferida (martes): las oleadas de migración se ejecutan todos los martes. Seleccione una fecha en un martes que no supere el 12/3/2019.
 
- Identificador de inquilino: número de 32 caracteres con este formato 0046728c-688a-4472-a38f-098fec60ac6x. Puede encontrar el identificador de inquilino en el portal de administración de Microsoft 365 en Azure AD o mediante el siguiente cmdlet de PowerShell:`Get-CsTenant | Select ObjectId`

Recibirá una confirmación por correo electrónico una vez que el inquilino se migre correctamente.

## <a name="auto-attendant-migration-guidelines"></a>Directrices de migración del operador automático

los administradores de Microsoft 365 y Office 365 organización deben volver a crear sus operadores automáticos de UM Online Exchange en el servicio Microsoft Cloud Auto Attendant y cambiar sus números de teléfono locales a ellos antes de la fecha de retirada del servicio UMO Exchange del 28 de febrero de 2020. Esta es la guía recomendada para migrar y probar correctamente nuevos operadores automáticos en la nube. Si tiene un gran número de operadores automáticos, puede usar los [scripts de migración de operador automático de mensajería unificada Exchange a operador automático](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) en la nube para simplificar la migración masiva de operadores automáticos.

### <a name="auto-attendant-setup"></a>Configuración del operador automático

Se recomienda encarecidamente que inicie la configuración de los nuevos operadores automáticos antes de tiempo para evitar problemas de último minuto y familiarizarse con la funcionalidad y la experiencia del servicio Operador automático en la nube. En el caso de los operadores automáticos que requieren una o varias características de brecha, puede crear y probar los operadores automáticos cuando las características de brecha estén disponibles para prepararse para la implementación. Para obtener más información sobre las características de brecha, consulte el [Apéndice](#appendix).

1. Use los cmdlets Exchange UMO para exportar la configuración de operadores automáticos existentes mediante [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Use el cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) en Exchange Online PowerShell para exportar los archivos multimedia de saludo (si se usan) y convertirlos a .mp3 formato.

3. Siga las instrucciones de [Planear operadores automáticos](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) en la nube y [Configurar un operador automático](/microsoftteams/create-a-phone-system-auto-attendant) en la nube para crear operadores automáticos mediante el centro de administración de Microsoft Teams o PowerShell.

4. Revise los saludos si las opciones del menú han cambiado.

5. Configure las transferencias a los grupos de respuesta mediante la solución alternativa "Transferencia automática de llamadas de operador a RTC" en la sección [Problemas conocidos](#known-issues) de este artículo.  

6. Pruebe los nuevos operadores automáticos llamándolos internamente o asignando un número de teléfono de prueba.  

### <a name="cutover"></a>Total

1. Cambie los números de teléfono de Exchange operadores automáticos de UMO a los nuevos operadores automáticos.
2. Mueva el URI sip del objeto de contacto a la cuenta de recursos.
3. Pruebe y valide los operadores automáticos mediante los números de teléfono recién asignados.

## <a name="appendix"></a>Apéndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de características de servicios basados en la nube de ExchUMO y Azure

| Servicio | Nivel de característica | Característica | Notas  | Máquina virtual en la nube/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Características del servicio| Compatibilidad con PBX de terceros    | Incluir todas las características proporcionadas a PBX de terceros, como MWI (indicador de mensaje en espera) mediante mensajes de notificación SIP de Exchange UM Online | N   | v    |
| VM | Características del servicio  | Soporte técnico Skype Empresarial Server   |  | v | v    |
| VM | Características del servicio | Soporte técnico Microsoft Teams|  | v | N    |
| VM | Características del servicio | eDiscovery y Hold  | Para la seguridad y el cumplimiento  | v | v    |
| VM | Características del servicio | Compatibilidad con reglas de Exchange | Para la seguridad y el cumplimiento  | v | v    |
| VM | Características del usuario | Acceso telefónico local RTC  | Acceso de suscriptor  | N | v    |
| VM | Características del usuario | Delegado  | correo electrónico de llamada perdida  | N | v    |
| VM | Características del usuario | Outlook Voice Access RTC   | Acceso de suscriptor  | N | v    |
| VM | Características del usuario | Acceso telefónico local mediante un punto de conexión autenticado | Llamada al servicio de correo de voz para escuchar mensajes de voz y cambiar la configuración del correo de voz| v | v    |
| VM | Características del usuario | Configuración del usuario para deshabilitar el correo de voz   |  | v | v    |
| VM | Características del usuario | Configuración del usuario para cambiar el saludo personal  |  | v | v    |
| VM | Características del usuario | Configuración del usuario para crear un saludo de OOF  |  | v | v    |
| VM | Características del usuario | Configuración del usuario para cambiar el idioma predeterminado  |  | v | v    |
| VM | Características del usuario | Configuración del usuario para sobrescribir el saludo predeterminado con TTS  |  | v | N    |
| VM | Características del usuario | Grabar saludos personales (dispositivo autenticado) |  | v | v    |
| VM | Características del usuario | Grabar saludos personales (RTC): reproducir en el teléfono |  | N | v    |
| VM | Características del usuario | Configuración del usuario para deshabilitar la transcripción |  | N | v    |
| VM | Características del usuario | Transcripción  |  | v | v    |
| VM | Características del usuario | MWI (indicador de mensaje en espera) mediante mensajes de notificación SIP |  | N | v    |
| VM | Características del usuario | Formato de archivo de audio MP3 en Outlook    |  | v | v    |
| VM | Características del usuario | Control de reproducción de velocidad variable |  | v | v    |
| VM | Características del usuario | Reenviar un correo de voz  | Reenviar un correo de voz recibido a otros usuarios | v | v    |
| VM | Características del usuario | Envío de un mensaje de voz a un grupo de usuarios  |Difusión del correo de voz   | N | v   |
| VM | Características del usuario | Notificación de correo de voz mediante SMS    | Los usuarios pueden recibir un SMS cuando tienen un nuevo correo de voz    | N | v    |
| VM | Características del usuario | Idiomas de saludo admitidos | Detalles aquí: [¿Qué son los operadores automáticos en la nube?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| VM | Características del usuario | Reglas de contestador automático |  | v | v    |
| VM | Características del usuario | Reproducir en el teléfono (RTC): para reproducir el mensaje | Llámame en mi celda para escuchar el mensaje de voz.  | N | v    |
| VM | Características del usuario | Reproducir en el teléfono (autenticación): para reproducir el mensaje | Llamarme en mi dispositivo autenticado  | N | v    |
| VM | Características del usuario | Buzón compartido entre varios usuarios |  | v | v    |
| VM | Características del autor de la llamada  | Experiencia del llamador: correo de voz protegido | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como protegido.| N | v    |
| VM | Características del autor de la llamada  | Experiencia del llamador: correo de voz privado | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como privado.  | N | v    |
| VM | Características del autor de la llamada  | Detección de silencio   |  | N | v    |
| VM | Características de Tenant-Admin | Correo de voz protegido en el nivel de servidor    | Tenant-admin puede configurar una regla de nivel de servicio para marcar el correo de voz entrante como protegido. | v | v    |
| VM | Características de Tenant-Admin | Cambio del límite de tiempo de duración de grabación  |     | v | v    |
| VM | Características de Tenant-Admin | Cambio del tiempo de espera de detección de silencio    |  | N/D    | v    |
| VM | Características de Tenant-Admin | Cambio del número de errores de entrada | CVM: codificado de forma rígida a 3 | N | v    |
| VM | Características de Tenant-Admin | Cambiar el idioma predeterminado |  | v | v    |
| VM | Características de Tenant-Admin | Deshabilitar o habilitar la transcripción |  | v | v    |
| VM | Características de Tenant-Admin | Deshabilitar o habilitar la notificación de llamada perdida |  | N | v    |
| VM | Características de Tenant-Admin | Ayudar a Microsoft a mejorar la vista previa del correo de voz    |  | v | v    |
| VM | Características de Tenant-Admin | Personalización de mensajes de texto para usuarios habilitados|  | N/D    | v    |
| VM | Características de Tenant-Admin | Enmascaramiento de palabras soeces de transcripción|  | v | N    |
| VM | Características de Tenant-Admin | Directiva de correo de voz    |   | v | v    |
| VM | Características de Tenant-Admin | Administración del portal web   |  | CY19   | v    |
| VM | Características de Tenant-Admin | PowerShell   |  | v | v    |
| Mensajería unificada | Características del usuario | Indicador de mensaje en espera (MWI) en Skype Empresarial teléfonos certificados   |Puede ser proporcionado por un asociado de teléfono  | No | Sí    |
| AA | Características del servicio | Compatibilidad con PBX de terceros de AA    |  | N | v    |
| AA | Características del servicio | Soporte técnico Skype Empresarial Server   |  | v | v    |
| AA | Características del servicio | Soporte técnico Microsoft Teams|  | v | N    |
| AA | Características del servicio | Marcado por nombre, entrada DTMF    |  | v | v    |
| AA | Características del servicio | Marcado por nombre, entrada de voz  |  | v | v    |
| AA | Características del servicio | Compatibilidad con varios idiomas | Detalles del idioma aquí: [¿Qué son los operadores automáticos en la nube?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| AA | Características del servicio | Transferencia al operador, CQ o un usuario |  | v | v    |
| AA | Características del servicio | Transferencia al número RTC internamente (DID RNL)  |  | v | v    |
| AA | Características del servicio | Transferencia al número RTC externamente  |  | Consulte la sección Problemas conocidos a continuación | v    |
| AA | Características del servicio | Horario comercial |  | v | v    |
| AA | Características del servicio | Opciones de menú | Opciones de menú IVR  | v | v    |
| AA | Características del servicio | Asignación de un número RTC en la nube a AA |  | v | N    |
| AA | Características del servicio | Asignación de un número RTC local a AA  |  | v | v    |
| AA | Características del servicio | Selección de usuario personalizada  | Permitir que los autores de llamadas lleguen a la lista personalizada de usuarios de la organización| v | v    |
| AA | Características del servicio | Tratamiento fuera del horario laboral y festivos  |  | v | v    |
| AA | Características del servicio | Saludo personalizado con texto a voz  |  | v | v    |
| AA | Características del servicio | Marcado de extensión   | Llegar a un usuario marcando su extensión  | v   | v    |
| AA | Características del servicio | Buzón de correo para que los autores de llamadas de AA dejen un mensaje    |  | v   | v    |
| AA | Características del servicio | Varias asignaciones de números RTC a un AA|  | v | v    |
| AA | Características de Tenant-Admin | Administración del portal web   |  | v | N    |
| AA | Características de Tenant-Admin | Cmdlets de PowerShell  |  | v | v    |
| Fax| Características del servicio | Integración de fax|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de prueba sugerido y validación posterior a la migración para administradores

Para validar que los usuarios se han migrado a Correo de voz en la nube, deje un correo de voz a un usuario y compruebe el cuerpo del mensaje en Outlook. Correo de voz en la nube mensajes tienen un pie de página que dice:

"Gracias por usar transcripción! Si no ve una transcripción anterior, se debe a que la calidad de audio no era lo suficientemente clara como para transcribir".

Al probar la funcionalidad del correo de voz después de migrar los usuarios, asegúrese de tener en cuenta los siguientes escenarios:

- Valide el acceso del correo de voz en todos los tipos de punto de conexión de la organización, como aplicaciones y teléfonos IP.
- Valide con los usuarios de ejemplo que los saludos personalizados configurados se reproducen a los autores de llamadas.
- Si su organización tiene un requisito legal o de cumplimiento para deshabilitar la transcripción de los usuarios, asegúrese de que está deshabilitada después de la migración. Para obtener más información, consulte [Configuración de Correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail).
- Si ha configurado anteriormente Exchange directivas y reglas de máquina virtual, asegúrese de que son eficaces.
- Familiarícese con los cmdlets de PowerShell del servicio Correo de voz en la nube para cambiar la configuración del usuario.  

### <a name="user-experience-impact"></a>Impacto en la experiencia del usuario

A continuación se muestra información general sobre la experiencia de migración del correo de voz del usuario final.


|Experiencia  |Cambio en la experiencia del usuario|
|---------|---------|
|Notificación por correo electrónico | Sin cambios<br>No se envía ningún correo electrónico a los usuarios que les notifiquen sobre la activación o migración de la cuenta de correo de voz. |
|Acceso a mensajes anteriores | Sin cambios<br>Los usuarios tienen acceso a sus mensajes de correo de voz anteriores en todos los puntos de conexión admitidos. |
|Recepción de máquinas virtuales en Outlook, aplicaciones SFB| Sin cambios<br>Los usuarios siguen recibiendo sus mensajes de correo de voz en todos los puntos de conexión admitidos. |
|Transcripción | Mejorado<br>La transcripción de CVM tiene una tasa de precisión y lenguajes admitidos mucho más alta que ExchUMO. |
|Configuración del usuario | Nueva experiencia<br>Los usuarios pueden cambiar sus preferencias desde un Portal de configuración de usuarios (USP). Los usuarios pueden acceder a su USP desde un hipervínculo en su correo electrónico de correo de voz, o el botón User-Settings en su cliente SFB; https://aka.ms/vmsettings.
 |Características| Consulte la comparación del conjunto de características para obtener más información. |
|Outlook reglas para mensajes de máquina virtual | Sin cambios<br>Las reglas creadas anteriormente se aplicarán a los mensajes de CVM después de la migración.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Administración y aprovisionamiento de usuarios en CVM

Los nuevos usuarios de Skype Empresarial se aprovisionarán automáticamente para el correo de voz en la nube cuando se creen. No se requiere ninguna licencia o trabajo de administrador adicional para aprovisionar nuevos usuarios de correo de voz. Consulte [Configuración de Correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail) para obtener información sobre la administración de directivas para usuarios nuevos y existentes.

### <a name="admin-auto-attendant-management-experience"></a>Administración experiencia de administración del operador automático

Para más información sobre los operadores automáticos, consulte [Configuración de un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Problemas conocidos

#### <a name="greeting-inconsistencies"></a>Incoherencias de saludo

Es posible que el acceso de suscriptor siga funcionando para el inquilino hasta que el servicio se retire por completo, incluso después de que todos los usuarios se hayan migrado a Correo de voz en la nube. Para evitar la confusión del usuario y una experiencia incoherente, deshabilite el acceso del suscriptor, ya que los saludos cambian después de la migración. Para ello, quite el contacto EXUM para cada línea de acceso de suscriptor mediante `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`.

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Transferencia automática de llamadas de operador a RTC

Para transferir una llamada de operador automático a un número de teléfono RTC externo a través de Skype Empresarial Server o un servicio de grupo de respuesta (RGS) en Skype Empresarial Server, cree un nuevo usuario local con el reenvío de llamadas establecido en el número de teléfono RTC o el número de teléfono RGS. El usuario debe estar habilitado y configurado correctamente para Telefonía IP empresarial y tener asignada una directiva de voz.

#### <a name="shared-mailbox-is-still-accessible"></a>El buzón compartido sigue siendo accesible

Un buzón compartido configurado mediante Exchange UM Online sigue recibiendo mensajes después de la migración a CVM y es accesible para los usuarios a través de Outlook. Sin embargo, el acceso para cambiar los mensajes de saludo de estos buzones no estará disponible una vez migrado a CVM. Los clientes con buzones compartidos que se usan para capturar autores de llamadas de operador automático deben aprovechar las funcionalidades de buzón compartido de operadores automáticos y colas de llamadas una vez publicados (ETA de octubre de 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Pantallas de banner "Username is not using Skype Empresarial" (El nombre de usuario no usa Skype Empresarial)

El servicio CVM se basa en la infraestructura de Microsoft Teams, y las llamadas de un cliente de Skype Empresarial podrían hacer que un banner de información se muestre en el cliente que dice: "Username is not using Skype Empresarial. Para obtener una experiencia más completa, cambie a Teams o inicie una reunión de Skype".
Asegúrese de actualizar el cliente Skype Empresarial de los usuarios a la actualización de cliente C2R más reciente para evitar que aparezca este banner.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>"Configurar correo de voz" le lleva a OWA

Al hacer clic en Configurar correo de **voz** desde el cliente, se seguirán llevando Skype Empresarial Server clientes de 2015/2013 a la página del portal Office Web Access (OWA) después de la migración a CVM. Todas las configuraciones se han quitado de la pestaña Correo de voz en OWA y se mostrará un banner con un vínculo de redirección para llevar a los usuarios al portal de configuración de usuarios de CVM.

#### <a name="changing-greeting-remotely"></a>Cambiar el saludo de forma remota

El acceso del suscriptor RTC no se admite en el CVM. Para los usuarios que necesitan cambiar su saludo de forma remota, se ha agregado una opción de menú "Cambiar el saludo" al servicio IVR de correo de voz para clientes móviles. Los usuarios pueden llamar a este servicio presionando y manteniendo presionada la tecla "1" en el panel de marcado del cliente móvil.