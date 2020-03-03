---
title: Soporte de migración en línea de mensajería unificada de Exchange
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
description: Microsoft retira el servicio en línea de mensajería unificada (ExchUMO) de Exchange antes del 28 de febrero de 2020. En este artículo se resumen lo que los clientes afectados deben conocer y hacer para planear su continuidad empresarial.
ms.openlocfilehash: f6adb1636d6a40e41b006c3981dc4d21ba503289
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374307"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Soporte de migración en línea de mensajería unificada de Exchange

> [!IMPORTANT]
> **El servicio de mensajería unificada de Exchange Online está fuera de soporte a partir del 28 de febrero de 2020 a la hora del Pacífico. Todas las cuentas de correo de voz se han migrado al servicio de correo de voz en la nube de Microsoft. El tráfico del operador automático restante no se supervisará y podría verse afectado en cualquier momento.**

En referencia al [anuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) el 8 de febrero de 2019, Microsoft retira el servicio en línea de mensajería unificada de Exchange (ExchUMO) antes del 28 de febrero de 2020. En este artículo se ofrece un resumen de lo que los clientes afectados deben conocer y hacer para planear su continuidad empresarial.
 
ExchUMO es implementado por los clientes para los servicios de correo de voz, operador automático, cola de llamadas y servicios de integración de fax. Microsoft planea ayudar a los clientes a migrar a servicios de sistema telefónico que ya admiten miles de clientes en Skype empresarial online y Microsoft Teams.

El correo de voz es principalmente una migración controlada por Microsoft; es posible que se requiera la implicación y/o la inversión del administrador para un subconjunto de clientes. Operador automático es una migración controlada por el administrador; tendrá que volver a crear los árboles de operadores automáticos existentes de ExchUMO en el servicio en la nube del operador automático de la nube. Los clientes que consumen cualquiera de las características de ExchUMO con una PBX de terceros no se migrarán a servicios en la nube de Skype porque no admiten sistemas PBX de terceros. En [este blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)se anunció un plan de jubilación para la compatibilidad de terceros y los clientes de este modelo de implementación pueden migrar a sus usuarios a uno de los servicios/plataformas de comunicaciones unificadas de Microsoft o adquirir una solución de correo de voz de terceros o operador automático para estos usuarios. La integración de faxes no es compatible con los servicios basados en la nube; los clientes deberán migrar a una solución de terceros.

### <a name="who-is-affected"></a>¿A quién afecta?

Los clientes que consumen cualquiera de las siguientes características del servicio en línea de mensajería unificada de Exchange se ven afectados:

- Servicio de correo de voz
- Servicio de operador automático
- Servicio de cola de llamadas
- Integración de fax

> [!Note]
> Los clientes que usen el servidor de Exchange local con mensajería unificada no se verán afectados. 

Obtenga más información sobre la experiencia de usuario y administrador impacto en el impacto de la [experiencia del usuario](#user-experience-impact).

## <a name="migration-plan-overview"></a>Información general del plan de migración

Microsoft ha identificado varias implementaciones de clientes que consumen características de ExchUMO y que ayudarán a migrar a los clientes en función del siguiente plan. 

|Grupo de clientes |Escala de tiempo  |Detalles  |
|---------|---------|---------|
|Clientes que están listos para migrar<br><br>Características que se van a migrar:<br><ul><li>Correo de voz</ul>   |   Marzo: 2019 de mayo  |Ejemplos:<ul><li>    Clientes con una implementación y un uso sencillos de correo de voz<li>Clientes que tienen todos los requisitos establecidos para que Microsoft ejecute la migración<ul>|
|Clientes con requisitos previos<br><br>Características que se van a migrar:<br><ul><li>Correo de voz<li>Operador automático<li>Cola de llamadas</ul> |  Mayo, 2019 de diciembre |Ejemplos: <br><ul><li>La configuración híbrida no está completa<li>Los números híbridos de RTC no se configuran</ul>|
|Clientes que requieren la implicación del administrador & la inversión del cliente<br><br>Características que se van a migrar:<ul><li>correo de voz<li>Operador automático<li>Colas de llamadas<li>Integración de fax</ul>| En febrero de 2020  | Ejemplos: <br><ul><li>El servicio ExchUMO está consumido por PBX de terceros<li>Clientes con requisitos de acceso de suscriptor RTC<li>Clientes de SFB 2010 (no admitido)<li>Integración de fax</ul> |

## <a name="voicemail-migration-steps"></a>Pasos para la migración del correo de voz

1.  **Obtener información**
 
    Familiarícese con el [anuncio del blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) y este artículo para planear una migración sin problemas para los usuarios. Consulte [comprobar el correo de voz y las opciones de Skype empresarial](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obtener más información sobre las funciones del correo de voz del sistema telefónico.  
 
2.  **Establecer una topología híbrida de Skype empresarial**

    Si no tiene establecida una topología híbrida de Skype empresarial, debe hacerlo para habilitar una migración sin problemas de los usuarios de correo de voz. Consulte [configurar Skype empresarial híbrido](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obtener más información. 

    > [!Note]
    > No es necesario migrar los usuarios a en línea para la migración del servicio de correo de voz. Sin embargo, para que los usuarios locales puedan aprovechar el servicio de correo de voz de sistema telefónico, se debe establecer una topología híbrida.

3. **Planeación de la migración del operador automático**
    
    Los administradores pueden empezar a migrar sus operadores automáticos de ExchUMO al operador automático de la nube en cualquier momento. Consulte [configurar un operador automático de la nube](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para obtener más información. Microsoft sigue ofreciendo funciones adicionales de operador automático que los clientes pueden considerar necesarios para su migración, los administradores deben evaluar el conjunto de características y migrar sus instancias del operador automático en consecuencia. Para comparar la lista de características, consulte la matriz de características de los [servicios basados en la nube de ExchUMO y Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planeación de las pruebas y la validación posterior a la migración del correo de voz**

    La migración del correo de voz está controlada por Microsoft. No es necesario que los administradores hagan nada, dado que se ha establecido la topología híbrida de requisitos previos. Microsoft realiza la validación y las pruebas necesarias para asegurarse de que no se interrumpa la migración del correo de voz de los usuarios. Se recomienda a los administradores que realicen pruebas y validaciones en su lado. Vea el [plan de pruebas sugerido y la validación posterior a la migración para administradores](#suggested-test-plan-and-post-migration-validation-for-admins) de un plan de pruebas recomendado. 

    > [!Note]
    > Lync Server 2010 no es compatible. Si está en una implementación de servidor 2010, debe planear una actualización de servidor o considerar la posibilidad de migrar los usuarios a Microsoft Teams o Skype empresarial online.  

5. **Supervisar el centro de notificaciones de administrador**

    Consulte un aviso en el centro de notificaciones del administrador con más detalles y escala temporal sobre la migración de los usuarios. Las notificaciones se envían al menos 30 días antes del período de migración. 

    > [!Note]
    > Si recibió una notificación con la escala de tiempo de la migración de los usuarios y desea posponer su migración por un motivo crítico para la empresa, puede ponerse en contacto con el soporte técnico de Microsoft. Tenga en cuenta que no puede posponer la migración más allá de la fecha de retiro, 28 de febrero de 2020. Para los clientes que puedan tener más preguntas, póngase en contacto con su equipo de cuenta o soporte técnico de Microsoft. Los clientes que ya usan Office 365 pueden enviar un caso de soporte técnico a través del portal de administración de Office 365. 

6. **Considere la posibilidad de optar por una migración planeada**

    Puede participar para una migración del servicio de correo de voz planeada a CVM. Antes de optar a, revise los detalles de este artículo, especialmente las secciones siguientes:

    - Pasos de la migración (esta sección)
    - Matriz de características de servicios basados en la nube de ExchUMO y Azure
    - Impacto de la experiencia del usuario

    Al elegir una migración administrada, no recibirá una notificación de 30 días previa a la migración en el centro de mensajes del portal de administración de Microsoft 365.
 
    Para participar en una migración planificada, envíe una solicitud de correo electrónico desde la dirección de correo electrónico del administrador a [CVM@microsoft.com](mailto:cvm@microsoft.com) con la siguiente información:

    - Fecha preferida (martes): las ondas de migración se ejecutan cada martes. Seleccione una fecha en un martes no superior a 12/3/2019.
 
    - IDENTIFICADOR de espacio empresarial: número de 32 caracteres en este formato 0046728c-688a-4472-a38f-098fec60ac6x. Puede encontrar el identificador de inquilino en el portal de administración de Microsoft 365 en Azure AD o mediante el siguiente cmdlet de PowerShell:`Get-CsTenant | Select ObjectId`
 
    Recibirá una confirmación por correo electrónico una vez que el inquilino se haya migrado correctamente.

## <a name="auto-attendant-migration-guidelines"></a>Instrucciones de migración del operador automático

Los administradores de inquilinos de Office 365 necesitan volver a crear los operadores automáticos de mensajería unificada de Exchange en el servicio de operador automático de la nube de Microsoft y cambiar sus números de teléfono locales antes del 28 de febrero de 2020, que es cuando el servicio Exchange UMO se tirar. Esta es la pauta recomendada para migrar y probar correctamente nuevos operadores automáticos de la nube. Si tiene un gran número de operadores automáticos, puede usar el [operador automático de mensajería unificada de Exchange para los scripts de migración de operadores](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automáticos de la nube para simplificar la migración masiva de los operadores automáticos.

### <a name="setup"></a>Configuración

Le recomendamos encarecidamente que inicie la configuración de los nuevos operadores automáticos para evitar problemas de los últimos minutos y para familiarizarse con la funcionalidad y la experiencia del servicio de operador automático de la nube. En el caso de los operadores automáticos que requieran una o varias características de brecha, puede crear y probar los operadores automáticos cuando las características de brecha estén disponibles para prepararse para la implementación. Para obtener más información acerca de las características de brechas, vea el [Apéndice](#appendix).

1. Use los cmdlets de Exchange UMO para exportar la configuración de los operadores automáticos existentes mediante [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Use el cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) en Exchange Online PowerShell para exportar los archivos multimedia de saludo (si se usan) y convertirlos al formato. mp3.
3. Siga las instrucciones del [plan de operadores](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) automáticos en la nube y [Configure un operador automático de la nube](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para crear operadores automáticos mediante el centro de administración de Microsoft Teams o PowerShell.
4. Revise sus saludos si las opciones de menú han cambiado.
5. Configure las transferencias a los grupos de respuesta mediante la solución "transferencia automática de llamadas de operador automático a RTC" en la sección [problemas conocidos](#known-issues) de este artículo.  
6. Pruebe los nuevos operadores automáticos. Para realizar las pruebas, llámelos internamente o asigne un número de teléfono de prueba.  

### <a name="cutover"></a>Total

1. Cambiar los números de teléfono de los operadores automáticos de Exchange UMO a los nuevos operadores automáticos.
2. Mueva el URI de SIP del objeto Contact a la cuenta de recurso.
3. Pruebe y valide los operadores automáticos mediante los números de teléfono asignados recientemente. 

## <a name="appendix"></a>Apéndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de características de servicios basados en la nube de ExchUMO y Azure

| Servicio | Nivel de característica | Característica | Notas  | VM en la nube/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Características del servicio| Admitir PBX de terceros    | Incluir todas las características proporcionadas a PBX de terceros, como MWI (indicador de mensaje en espera) mediante SIP Notify online Messages from Exchange UM online | N   | v    |
| VM | Características del servicio  | Compatibilidad con Skype empresarial Server   |  | v | v    |
| VM | Características del servicio | Soporte técnico de Microsoft Teams|  | v | N    |
| VM | Características del servicio | eDiscovery y retención  | Para la seguridad y el cumplimiento  | v | v    |
| VM | Características del servicio | Compatibilidad con las reglas de Exchange | Para la seguridad y el cumplimiento  | v | v    |
| VM | Características de usuario | Acceso telefónico RTC  | Acceso de suscriptor  | N | v    |
| VM | Características de usuario | RTC de Outlook Voice Access   | Acceso de suscriptor  | N | v    |
| VM | Características de usuario | Acceso telefónico local con un extremo autenticado | Llamar al servicio de correo de voz para escuchar mensajes de voz y cambiar la configuración del correo de voz| v | v    |
| VM | Características de usuario | Configuración del usuario para deshabilitar el correo de voz   |  | v | v    |
| VM | Características de usuario | Configuración del usuario para cambiar el saludo personal  |  | v | v    |
| VM | Características de usuario | Configuración de usuario para crear un saludo para OOF  |  | v | v    |
| VM | Características de usuario | Configuración del usuario para cambiar el idioma predeterminado  |  | v | v    |
| VM | Características de usuario | Configuración de usuario para sobrescribir el saludo predeterminado con TTS  |  | v | N    |
| VM | Características de usuario | Grabación de saludos personales (dispositivo autenticado) |  | v | v    |
| VM | Características de usuario | Registrar saludos personales (RTC): reproducción en teléfono |  | N | v    |
| VM | Características de usuario | Configuración del usuario para deshabilitar la transcripción |  | N | v    |
| VM | Características de usuario | Cripción  |  | v | v    |
| VM | Características de usuario | Correo de voz de visual en todos los extremos   | Con control de usuario para reproducir, eliminar, indicador de mensaje en espera y alternar estado, en todos los extremos admitidos  | v | v    |
| VM | Características de usuario | Formato de archivo de audio MP3 en Outlook    |  | v | v    |
| VM | Características de usuario | Control de reproducción de velocidad variable |  | v | v    |
| VM | Características de usuario | Reenviar un correo de voz  | Reenviar correo de voz recibido a otros usuarios | v | v    |
| VM | Características de usuario | Enviar un mensaje de voz a un grupo de usuarios  |Difusión de correo de voz   | N | v   |
| VM | Características de usuario | Notificación de correo de voz mediante SMS    | Los usuarios pueden recibir un SMS cuando tienen un nuevo correo de voz    | N | v    |
| VM | Características de usuario | Idiomas de saludo compatibles | Detalles aquí:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| VM | Características de usuario | Reglas de contestador automático |  | v | v    |
| VM | Características de usuario | Reproducir en teléfono (RTC): mensaje para reproducir | Llamar a me en mi celda para escuchar el mensaje de voz  | N | v    |
| VM | Características de usuario | Reproducir en teléfono (autenticación): mensaje para reproducir | Llamarme en mi dispositivo autenticado  | v | v    |
| VM | Características de usuario | Buzones compartidos entre varios usuarios |  | v | v    |
| VM | Características del autor de la llamada  | Experiencia del autor de la llamada: buzón de voz protegido | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como protegido| N | v    |
| VM | Características del autor de la llamada  | Experiencia del autor de la llamada: correo de voz privado | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como privado  | N | v    |
| VM | Características del autor de la llamada  | Detección en silencio   |  | N | v    |
| VM | Inquilino-características de administración | Correo de voz protegido en el nivel de servidor    | Tenant-admin puede configurar una regla de nivel de servicio para marcar el correo de voz entrante como protegido. | v | v    |
| VM | Inquilino-características de administración | Límite de tiempo de duración de grabación de cambios  |     | v | v    |
| VM | Inquilino-características de administración | Cambiar el tiempo de espera de detección de silencio    |  | N/D    | v    |
| VM | Inquilino-características de administración | Cambiar el número de errores de entrada | CVM: codificado de forma rígida en 3 | N | v    |
| VM | Inquilino-características de administración | Cambiar el idioma predeterminado |  | v | v    |
| VM | Inquilino-características de administración | Deshabilitar o habilitar la transcripción |  | v | v    |
| VM | Inquilino-características de administración | Habilitar o deshabilitar la notificación de llamadas perdidas |  | N | v    |
| VM | Inquilino-características de administración | Ayudar a Microsoft a mejorar la vista previa del correo de voz    |  | v | v    |
| VM | Inquilino-características de administración | Personalizar mensaje de texto para usuarios habilitados|  | N/D    | v    |
| VM | Inquilino-características de administración | Enmascaramiento de blasfemias de transcripción|  | v | N    |
| VM | Inquilino-características de administración | Directiva de correo de voz    |   | v | v    |
| VM | Inquilino-características de administración | Administración de portal web   |  | CY19   | v    |
| VM | Inquilino-características de administración | PowerShell   |  | v | v    |
| AQ | Características del servicio | AA admite PBX de terceros    |  | N | v    |
| AQ | Características del servicio | Compatibilidad con Skype empresarial Server   |  | v | v    |
| AQ | Características del servicio | Soporte técnico de Microsoft Teams|  | v | N    |
| AQ | Características del servicio | Marcado por nombre, entrada DTMF    |  | v | v    |
| AQ | Características del servicio | Marcado por nombre, entrada de voz  |  | v | v    |
| AQ | Características del servicio | Compatibilidad con varios idiomas | Detalles del idioma aquí:https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| AQ | Características del servicio | Transferir a operador, CQ o un usuario |  | v | v    |
| AQ | Características del servicio | Transferir al número de RTC internamente (RNL)  |  | v | v    |
| AQ | Características del servicio | Transferir a un número de RTC de forma externa  |  | Consultar la sección problemas conocidos a continuación | v    |
| AQ | Características del servicio | Horario comercial |  | v | v    |
| AQ | Características del servicio | Opciones de menú | Opciones del menú IVR  | v | v    |
| AQ | Características del servicio | Asignación de un número de RTC en la nube a AA |  | v | N    |
| AQ | Características del servicio | Asignar un número RTC local a AA  |  | v | v    |
| AQ | Características del servicio | Selección de usuario personalizada  | Habilitar a los autores de las llamadas para obtener una lista personalizada de los usuarios de la organización| v | v    |
| AQ | Características del servicio | Tratamiento fuera de horario y festivos  |  | v | v    |
| AQ | Características del servicio | Saludo personalizado con texto a voz  |  | v | v    |
| AQ | Características del servicio | Marcado de extensión   | Ponerse en acceso a un usuario marcando su extensión  | v   | v    |
| AQ | Características del servicio | Buzón de correo para que los autores de llamadas de AA dejen un mensaje    |  | v   | v    |
| AQ | Características del servicio | Varias asignaciones de números RTC a un AA|  | v | v    |
| AQ | Inquilino-características de administración | Administración de portal web   |  | v | N    |
| AQ | Inquilino-características de administración | Cmdlets de PowerShell  |  | v | v    |
| Fax| Características del servicio | Integración de fax|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de pruebas sugerido y validación posterior a la migración para administradores

Para validar que los usuarios se han migrado al correo de voz de la nube, deje un correo de voz a un usuario y compruebe el cuerpo del mensaje en Outlook.  Los mensajes de correo de voz en la nube tienen un pie de página que dice:

**Gracias por usar transcripción. Si no ve una transcripción antes, es porque la calidad del audio no es lo suficientemente clara como para transcribirla.**

Al probar la funcionalidad de correo de voz después de migrar los usuarios, asegúrese de tener en cuenta los siguientes escenarios:

- Validar el acceso de correo de voz en todos los tipos de extremos de la organización: aplicaciones y teléfonos IP. 
- Validar con usuarios de muestra que se reproducen los saludos personalizados configurados para las personas que llaman.   
- Si su organización tiene un requisito legal o de cumplimiento normativo para deshabilitar la transcripción para los usuarios, asegúrese de que esté deshabilitada después de la migración. Para obtener más información, consulte [configurar el correo de voz de la nube](/microsoftteams/set-up-phone-system-voicemail).
- Si ha configurado previamente directivas y reglas de VM de Exchange, asegúrese de que son efectivas.
- Familiarícese con los cmdlets de PowerShell del servicio de correo de voz en la nube para cambiar la configuración del usuario.  

### <a name="user-experience-impact"></a>Impacto de la experiencia del usuario

A continuación, se encuentra una introducción a la experiencia de migración del correo del usuario final.


|Experiencia  |Cambio en la experiencia del usuario|
|---------|---------|
|Notificación de correo electrónico | Sin cambios<br>No se envía un correo electrónico a los usuarios que les notifica sobre la activación o migración de cuentas de correo de voz. |
|Acceso a mensajes anteriores | Sin cambios<br>Los usuarios tienen acceso a los mensajes de correo de voz anteriores en todos los extremos admitidos. |
|Recibir una máquina virtual en Outlook, SFB apps| Sin cambios<br>Los usuarios continúan recibiendo los mensajes de correo de voz en todos los extremos admitidos. |
|Cripción | Mejor<br>La transcripción de CVM tiene una tasa de precisión muy superior e idiomas admitidos que ExchUMO. |
|Configuración de usuario | Nueva experiencia<br>Los usuarios pueden cambiar sus preferencias de un portal de configuración de usuario (USP). Los usuarios pueden acceder a su USP desde un hipervínculo en su correo de voz o el botón de configuración del usuario en su cliente de SFB; https://aka.ms/vmsettings.   
 |Características| Vea la comparación de los conjuntos de características para obtener más información. |
|Reglas de Outlook para mensajes de VM | Sin cambios<br>Las reglas creadas anteriormente se aplicarán a los mensajes de CVM después de la migración.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Administración y aprovisionamiento de usuarios en CVM

Los nuevos usuarios de Skype empresarial se aprovisionarán automáticamente para el correo de voz de nube cuando se cree. No se requiere ninguna licencia o trabajo administrativo adicional para aprovisionar nuevos usuarios de correo de voz. Consulte [configurar el correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail) para obtener más información sobre la administración de directivas para los usuarios nuevos y existentes.

#### <a name="admin-auto-attendant-management-experience"></a>Experiencia de administración del operador automático de administración

Para obtener más información sobre los operadores automáticos, consulte [configurar un operador automático de la nube](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

#### <a name="known-issues"></a>Problemas conocidos

**Transferencia de llamadas de operador automático a RTC** Se recomienda a los clientes configurar una solución temporal para cumplir los requisitos de transferencia de una llamada de operador automático a un número de RTC externo o a una instancia de RGS. 
 
Se identificó un problema durante el control de calidad con la característica transferencia fuera del número RTC, que no se va a reparar en el tiempo para que los clientes inicien la migración del servicio Exchange UMO antes de la fecha de retiro programada del 28 de febrero de 2020. Como solución alternativa, los administradores pueden transferir a los autores de llamadas de operador automáticos a un usuario virtual local con una configuración de reenvío de llamada activa al número de teléfono de RTC o número de teléfono RGS deseado. 
 
Experiencia esperada
- Los administradores no necesitan obtener una licencia para el usuario virtual, ya que se trata de una solución alternativa. 
- Los administradores pueden manipular el identificador de llamada que verá el receptor de RTC asignando el número deseado al usuario virtual o usando las funciones de manipulación de dígitos de SBC.
- Los autores de llamadas RTC no experimentarán ningún retraso durante la transferencia de llamadas y seguirán viendo el identificador de llamada del operador automático una vez que la transferencia se haya realizado correctamente.  

**Buzón compartido:** Un buzón compartido que se configura con la mensajería unificada en línea de Exchange seguirá recibiendo mensajes después de migrarlos a CVM y seguirá siendo accesible para los usuarios a través de Outlook. Sin embargo, el acceso para cambiar los mensajes de saludo de estos buzones no estará disponible una vez que se migre a CVM. Los clientes con buzones compartidos que se usan para capturar a los autores de llamadas de operador automático deben aprovechar las capacidades de buzón de correo compartido de las colas de llamadas y los operadores automáticos una vez lanzado (ETA octubre de 2019).
  
**Actualización a Banner de Teams en el cliente de SFB:** El servicio CVM se basa en la infraestructura de Microsoft Teams; las llamadas a él desde el cliente de Skype empresarial pueden hacer que se muestre un banner de información en el cliente que diga: "el nombre de usuario no usa Skype empresarial. Para obtener una experiencia más completa, cambie a teams o inicie una reunión de Skype. "
Asegúrese de actualizar el cliente de Skype empresarial de sus usuarios a la actualización de cliente de C2R más reciente para evitar que aparezca este banner.
  
**Configurar el correo de voz le llevará a OWA:** Si se hace clic en "configurar correo de voz" desde el cliente, los clientes de Skype empresarial Server 2015/2013 podrán seguir recibiendo la página del portal de Office Web Access (OWA) después de la migración a CVM. Se ha quitado toda la configuración de la ficha correo de voz de OWA y se mostrará un titular con un vínculo de redirección para llevar a los usuarios al portal de configuración de usuario de CVM.
 
**Cambiar el acceso móvil a saludo:** El acceso de suscriptor de RTC no se admite en CVM. Para los usuarios que necesiten cambiar su saludo de forma remota, se agrega una opción de menú "cambiar el saludo" al servicio de correo de voz para clientes móviles. Para llamar a este servicio, los usuarios pueden presionar y mantener presionada la tecla "1" en el control de marcado del cliente móvil.
