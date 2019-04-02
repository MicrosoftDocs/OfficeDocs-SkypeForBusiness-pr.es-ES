---
title: Soporte de migración en línea de la mensajería unificada de Exchange
ms.author: heidip
author: heidip
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft retira el servicio Exchange Unified Messaging en línea (ExchUMO) en febrero de 2020. En este artículo se resume qué afectados los clientes deben conocer y para planear su continuidad del negocio.
ms.openlocfilehash: 2622b95e8bae7d5721665c5691c1c76691207e74
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026247"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Soporte de migración en línea de la mensajería unificada de Exchange  

En relación con el [anuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) en el 8 de febrero de 2019 Microsoft es retirar el servicio de Exchange Unified Messaging en línea (ExchUMO) en febrero de 2020. En este artículo se ofrece un resumen de qué clientes afectados debe conocer y para planear su continuidad del negocio. 
 
ExchUMO se implementa por los clientes de correo de voz, operador automático o servicios de integración de fax. Planes de Microsoft ayudar a estos clientes a migrar a sus servicios basados en la nube que admiten miles de clientes ya en Skype para profesionales en línea y Microsoft Teams. 

Correo de voz es principalmente una migración basada en Microsoft; implicación de administración o inversión quizás sea necesaria para un subconjunto de los clientes. Operador automático es una migración controlada por el administrador; debe volver a crear los árboles de operador automático de ExchUMO existentes en el servicio de nube de operador automático de la nube. Los clientes que consumen cualquiera de las características de ExchUMO con un sistema PBX de terceros no se migrarán a los servicios de nube de Skype debido a que no son compatibles con sistemas PBX de terceros. Un plan de jubilación para ofrecer compatibilidad con aplicaciones de terceros se presentó el año anterior en [este blog](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
), y los clientes en este modelo de implementación pueden migrar sus usuarios a uno de plataformas y servicios de comunicaciones unificadas de Microsoft o adquirir un correo de voz de terceros o solución de operador automático para estos usuarios. No se admite la integración de fax en los servicios basados en la nube; los clientes necesitarán migrar a una solución de otro fabricante. 

### <a name="who-is-affected"></a>¿Quién se verá afectado?

Se ven afectados los clientes que consumen cualquiera de las siguientes características de Exchange Unified Messaging servicios en línea:

1. Servicio de correo de voz 
2. Servicio de operador automático 
3. Integración de fax 

> [!Note]
> No se ven afectados los clientes que usen cualquiera de los servidores de Exchange locales con la mensajería unificada. 

Más información sobre el usuario y el impacto de experiencia de administración en la [experiencia del usuario impacto](#user-experience-impact).

## <a name="migration-plan-overview"></a>Información general sobre el plan de migración

Microsoft ha identificado varias implementaciones de cliente que se consuman de las características de ExchUMO y ayudará a los clientes migrar según el plan siguiente. 


|Grupo de clientes |línea de tiempo  |Detalles  |
|---------|---------|---------|
|Clientes que están preparados para migrar<br><br>Características para migrar:<br><ul><li>Correo de voz</ul>   |   Marzo – de mayo de 2019  |Ejemplos:<ul><li>    Clientes con implementación simple de correo de voz y uso<li>Clientes que tienen todos los requisitos establecidos para Microsoft ejecutar la migración<ul>|
|Clientes con los requisitos previos<br><br>Características para migrar:<br><ul><li>Correo de voz<li>Operador automático</ul> |  Es posible que – diciembre de 2019 |Ejemplos: <br><ul><li>Configuración híbrida no se ha establecido/completado<li>No configurar los números de RTC híbrida</ul>|
|Clientes que requieren la inversión de los clientes de administración implicación &<br><br>Características para migrar:<ul><li>Mensaje de voz<li>Operador automático<li>Integración de fax</ul>| En febrero de 2020  | Ejemplos: <br><ul><li>Servicio de ExchUMO es usada por 3ª PBX de terceros<li>Clientes con los requisitos de acceso de suscriptor de RTC<li>Clientes en 2010 SFB (no compatible)<li>Integración de fax</ul> |

## <a name="migration-steps"></a>Pasos de migración

1.  **Obtener informados**
 
    Familiarícese con el [anuncio de blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) y este artículo para planear una migración sin problemas para los usuarios. Vea [Comprobación de Skype para correo de voz empresarial y opciones](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obtener información detallada sobre las funciones de correo de voz en la nube.  
 

2.  **Establecer un Skype para topología híbrida de negocio**

    Si no tiene un Skype para topología híbrida de negocio establecido, debe hacer para permitir una fácil migración de los usuarios de correo de voz. Para obtener más información, vea [Configurar Skype para entornos híbridos de negocio](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > No es necesario migrar los usuarios a en línea para la migración de servicio de correo de voz. Sin embargo, para que los usuarios locales aprovechar el servicio de correo de voz basados en la nube, una topología híbrida es deben establecerse.

3. **Planear la migración de operador automático**
    
    Los administradores pueden iniciar migrar a sus operadores automáticos de ExchUMO para el operador automático de la nube en cualquier momento. Para obtener más información, vea [configurar un operador automático de sistema telefónico](/MicrosoftTeams/create-a-phone-system-auto-attendant.md) . Planes de Microsoft para proporcionar funciones adicionales de operador automático que los clientes considerar críticos para su migración por de 2019 de marzo. Los administradores deben evaluar el conjunto de características y migrar sus instancias de operador automático en consecuencia. Para la comparación de la lista de características, consulte la [matriz de características de servicios basados en la nube ExchUMO y Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planear para su validación posterior a la migración de correo de voz y las pruebas**

    Migración de correo de voz es Microsoft controlados por; Los administradores no tienen que hacer nada, dado que haya establecido la topología híbrida de requisitos previos. Microsoft va a realizar la validación necesaria y las pruebas para asegurarse de que no se interrumpe la migración de correo de voz de los usuarios; Sin embargo, los administradores se aconseja a realizar las pruebas y la validación en el lado.  Consulte [sugeridos plan y validación posterior a la migración para los administradores de pruebas](#suggested-test-plan-and-post-migration-validation-for-admins) para un plan de pruebas recomendadas. 

    > [!Note]
    > Lync Server 2010 no se admite. Si se encuentra en una implementación de server 2010, debe planear una actualización del servidor o considere la posibilidad de migrar los usuarios a Microsoft Teams o Skype para profesionales en línea.  

5. **Supervisar el centro de administración de notificación**

    Tener en cuenta para una notificación en el centro de administración de notificación con más detalles y escala de tiempo con respecto a la migración de correo de voz de los usuarios. Las notificaciones se enviarán al menos 30 días antes de su período de migración. 

    > [!Note]
    > Si ha recibido una notificación con escala de tiempo de migración de los usuarios y que le gustaría posponer la migración por un motivo empresarial crítica, puede hacerlo por ponerse en contacto con Microsoft Support. Tenga en cuenta que no se puede posponer la migración más allá de la fecha de retirada, febrero de 2020. Para los clientes que tengan más preguntas, póngase en contacto con su equipo de cuentas o Microsoft Support. Los clientes que ya está usando Office 365 pueden enviar un caso de soporte técnico a través del portal de administración de Office 365. 

6. **Considere la posibilidad de optar en a partir de mayo de 2019**

    Puede participar en una migración de servicio de correo de voz anticipado por de mayo de 2019 (si no ha recibido una notificación de migración), para alinear la migración con una licencia anualidad o un administrador de vacaciones de los empleados o para evitar períodos críticos para el negocio. Obtener información detallada sobre el proceso de suscripción se actualizarán en este artículo antes de mayo de 2019.  

## <a name="appendix"></a>Apéndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de características de servicios basados en la nube ExchUMO y Azure 




| Servicio | Nivel de característica | Característica | Notas  | En la nube VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| MÁQUINA VIRTUAL  | Características del servicio| Admitir PBX de terceros 3rd    |  | N   | Y    |
| MÁQUINA VIRTUAL | Características del servicio  | Compatibilidad con Skype para Business Server   |  | Q1CY19 | Y    |
| MÁQUINA VIRTUAL | Características del servicio | Microsoft equipos de soporte técnico|  | Y | N    |
| MÁQUINA VIRTUAL | Características del servicio | exhibición de documentos electrónicos y retención  | Para el cumplimiento y seguridad  | S | S    |
| MÁQUINA VIRTUAL | Características del servicio | Compatibilidad con las reglas de Exchange | Para el cumplimiento y seguridad  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Acceso telefónico RTC  | Acceso de suscriptor  | N | Y    |
| MÁQUINA VIRTUAL | Características de usuario | RTC Outlook Voice Access   | Acceso de suscriptor  | N | Y    |
| MÁQUINA VIRTUAL | Características de usuario | Uso de un extremo autenticado en marcado | Llamar al servicio de correo de voz para escuchar mensajes de voz y cambiar la configuración de correo de voz| S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Configuración de usuario para deshabilitar el correo de voz   |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Configuración para cambiar el saludo personal de usuario  |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Si se establece en crear un saludo de fuera de la oficina del usuario  |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Configuración de usuario para cambiar el idioma predeterminado  |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Si se establece en Sobrescribir saludo predeterminado con TTS de usuario  |  | Y | N    |
| MÁQUINA VIRTUAL | Características de usuario | Saludos personales registros (dispositivo autenticado) |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Grabar saludos personales (RTC): reproducir en teléfono |  | N | Y    |
| MÁQUINA VIRTUAL | Características de usuario | Configuración de usuario para deshabilitar transcripción |  | N | Y    |
| MÁQUINA VIRTUAL | Características de usuario | Transcripción  |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Correo de voz Visual en todos los extremos   | Con el control de usuario para reproducir, eliminar, indicador de mensaje en espera y estado de alternancia, en todos los compatibles con extremos  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Formato de archivo de audio MP3 en Outlook    |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Control de reproducción de velocidad variable |  | S | S    |
| MÁQUINA VIRTUAL | Características de usuario | Reenviar un correo de voz  | Reenviar un correo de voz recibido a otros usuarios | Y | S    |
| MÁQUINA VIRTUAL | Características de usuario | Enviar un mensaje de voz a un grupo de usuarios  |Difusión de correo de voz   | N | Y   |
| MÁQUINA VIRTUAL | Características de usuario | Notificación de correo de voz con SMS    | Los usuarios pueden recibir un SMS cuando tienen un nuevo correo de voz    | N | Y    |
| MÁQUINA VIRTUAL | Características de usuario | Idiomas admitidos saludo | Detalles aquí:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | S    |
| MÁQUINA VIRTUAL | Características de usuario | Reglas de contestador automático |  | Q1CY19 | Y    |
| MÁQUINA VIRTUAL | Características de usuario | Reproducir en teléfono (RTC): para reproducir el mensaje | Llamarme en mi celda para escuchar el mensaje de voz  | N | Y    |
| MÁQUINA VIRTUAL | Características de usuario | Reproducir en teléfono (Auth) - para reproducir el mensaje | Llamarme en mi dispositivo autenticado  | Y | S    |
| MÁQUINA VIRTUAL | Características de usuario | Buzón compartido entre varios usuarios |  | Y | S    |
| MÁQUINA VIRTUAL | Características de autor de la llamada  | Experiencia del autor de la llamada: correo de voz protegido | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como protegido| N | Y    |
| MÁQUINA VIRTUAL | Características de autor de la llamada  | Experiencia del autor de la llamada: correo de voz privado | El autor de la llamada puede elegir una opción para marcar un mensaje grabado como privado  | N | Y    |
| MÁQUINA VIRTUAL | Características de autor de la llamada  | Detección del silencio   |  | N | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Nivel de servidor de correo de voz protegido    | Administración de inquilinos puede configurar una regla de nivel de servicio para marcar el correo de voz entrante como protegido | Y | S    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Límite de tiempo de duración de grabación de cambio  | CVM codificado de forma rígida en 5 minutos    | N | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Tiempo de espera de detección de silencio de cambio    |  | N/D    | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Cambiar el número de error de entrada | CVM: codificado 3 | N | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Cambiar el idioma predeterminado |  | Y | S    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Habilitar o deshabilitar la transcripción |  | Y | S    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Habilitar o deshabilitar la notificación de llamada perdida |  | N | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Ayudar a Microsoft a mejorar la vista previa de correo de voz    |  | S | S    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Personalizar el mensaje de texto para usuarios habilitados|  | N/D    | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Enmascaramiento de transcripción contenido ofensivo|  | Y | N    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Directiva de correo de voz    |   | S | S    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | Administración del portal Web   |  | CY19   | Y    |
| MÁQUINA VIRTUAL | Características de administración de inquilinos | PowerShell   |  | S | S    |
| AA | Características del servicio | Compatibilidad con AA 3rd terceros PBX    |  | N | Y    |
| AA | Características del servicio | Compatibilidad con Skype para Business Server   |  | S | S    |
| AA | Características del servicio | Microsoft equipos de soporte técnico|  | Y | N    |
| AA | Características del servicio | Marcado por nombre, entrada DTMF    |  | S | S    |
| AA | Características del servicio | Marcado por nombre, la entrada de voz  |  | S | S    |
| AA | Características del servicio | Compatibilidad con varios idioma | Detalles de idioma aquí:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| AA | Características del servicio | Transferir a operador, CQ o un usuario |  | S | S    |
| AA | Características del servicio | Transferir a número de RTC internamente (RNL DID)  |  | S | S    |
| AA | Características del servicio | Transferir a número de RTC externamente  |  | Q2CY19 | Y    |
| AA | Características del servicio | Horario comercial |  | S | S    |
| AA | Características del servicio | Opciones de menú | Opciones de menú IVR  | S | S    |
| AA | Características del servicio | Asignación de una número de RTC de nube a AA |  | Y | N    |
| AA | Características del servicio | Asignación de un número de RTC en prem a AA  |  | S | S    |
| AA | Características del servicio | Selección de usuario personalizada  | Habilitación de los autores de llamadas llegar a una lista personalizada de los usuarios de la organización| S | S    |
| AA | Características del servicio | Fuera del horario laboral y tratamiento de los días festivos  |  | S | S    |
| AA | Características del servicio | Saludo personalizado con texto a voz  |  | S | S    |
| AA | Características del servicio | Marcado de extensión   | Llegar a un usuario por su extensión de marcado  | CY19   | Y    |
| AA | Características del servicio | Buzón de correo para los autores de llamadas AA dejar un mensaje    |  | CY19   | Y    |
| AA | Características del servicio | Varios la asignación de números RTC a una AA|  | S | S    |
| AA | Características de administración de inquilinos | Administración del portal Web   |  | Y | N    |
| AA | Características de administración de inquilinos | Cmdlets de PowerShell  |  | S | S    |
| Fax| Características del servicio | Integración de fax|  | N | Y    |



### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de pruebas sugerida y validación posterior a la migración para los administradores

Al probar la funcionalidad de correo de voz después de que los usuarios se han migrado, asegúrese de que tener en cuenta los siguientes escenarios:

- Validar el acceso de correo de voz a través de todos los tipos de extremo de la organización: los teléfonos IP y aplicaciones. 
- Validar con los usuarios de ejemplo que se reproducen los saludos personalizados configurados para los autores de llamadas.   
- Si su organización tiene un requisito legal o de cumplimiento para deshabilitar transcripción para los usuarios, asegúrese de que está deshabilitado posterior a la migración. Para obtener más detalles, vea [Configurar el correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail).
- Si ha configurado anteriormente las reglas y las directivas de la máquina virtual de Exchange, asegúrese de que son eficaces.
- Familiarizarse con los cmdlets de PowerShell de servicio de correo de voz en la nube para cambiar la configuración de usuario.  


### <a name="user-experience-impact"></a>Impacto de la experiencia de usuario

La siguiente es una introducción a la experiencia de migración de usuario final correo de voz.


|Experiencia  |Cambio en la experiencia del usuario|
|---------|---------|
|Notificación de correo electrónico | Ningún cambio<br>No hay correo electrónico se envía a los usuarios notificarles acerca de la migración y activación de cuenta de correo de voz. |
|Acceso a los mensajes anteriores | Ningún cambio<br>Los usuarios tendrán acceso a sus mensajes de correo de voz anterior en todos los extremos compatibles. |
|Recibir VM en outlook, SFB aplicaciones| Ningún cambio<br>Los usuarios seguirán recibir sus mensajes de correo de voz en todos los extremos compatibles. |
|Transcripción | Mejorado<br>Transcripción CVM tiene una tasa de precisión mucho mayor y los idiomas compatibles que ExchUMO. |
|Configuración de usuario | Nueva experiencia<br>Los usuarios podrán cambiar sus preferencias de un Portal de configuración de usuario (USP). Los usuarios pueden tener acceso a su USP desde un hipervínculo en su correo electrónico de correo de voz, o en el botón Configuración del usuario en su cliente SFB; https://aka.ms/vmsettings.   
 |Características| Consulte la comparación de conjunto de características para obtener información detallada. |
|Reglas de Outlook para los mensajes de la máquina virtual | Ningún cambio<br>Anteriormente creadas reglas se aplicarán a los mensajes CVM después de la migración.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Administración de usuarios y el aprovisionamiento en CVM 

Skype para los nuevos usuarios de negocio se aprovisionará para correo de voz en el servicio de CVM cuando crea automáticamente. No se requiere ningún trabajo de administración adicionales o licencia para aprovisionar nuevos usuarios para correo de voz. Vea [Configurar el correo de voz en la nube](/microsoftteams/set-up-phone-system-voicemail) para obtener más información acerca de cómo administrar las directivas para los usuarios nuevos y existentes.

#### <a name="admin-auto-attendant-management-experience"></a>Experiencia de administración de operador automático de administración 

Vea [configurar un operador automático de sistema telefónico](/MicrosoftTeams/create-a-phone-system-auto-attendant.md) para obtener más información acerca de la configuración y administración de operadores automáticos. 
