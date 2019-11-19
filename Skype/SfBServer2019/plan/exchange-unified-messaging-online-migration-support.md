---
title: Soporte de migración en línea de la mensajería unificada de Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft está retirando el servicio en línea (ExchUMO) de mensajería unificada de Exchange hasta el 2020 de febrero. Este artículo resume lo que los clientes afectados deberían conocer y hacer para planear su continuidad empresarial.
ms.openlocfilehash: abaf16996a6d634bac77118e35b30228c2a43e07
ms.sourcegitcommit: 9ae5dadaab999acd061cc9418dbd55d98b82980e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2019
ms.locfileid: "38702311"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Soporte de migración en línea de la mensajería unificada de Exchange

En referencia al [anuncio](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) el 8 de febrero de 2019, Microsoft retira el servicio en línea (ExchUMO) de mensajería unificada de Exchange hasta el 2020 de febrero. Este artículo ofrece un resumen de lo que los clientes afectados deberían saber y hacer para planificar su continuidad empresarial. 
 
ExchUMO es implementado por los clientes para el buzón de voz, el operador automático, la cola de llamadas y los servicios de integración de fax. Microsoft planea ayudar a los clientes a migrar a servicios de sistema telefónico que ya admiten miles de clientes en Skype empresarial online y Microsoft Teams. 

El buzón de voz es principalmente una migración dirigida por Microsoft; es posible que se requiera la implicación e inversión del administrador para un subconjunto de clientes. El operador automático es una migración guiada por el administrador; tendrá que volver a crear los árboles de operadores automáticos de ExchUMO existentes en el servicio de nube de operador automático de la nube. Los clientes que consumen cualquiera de las características de ExchUMO con un PBX de terceros no se migrarán a los servicios en la nube de Skype porque no admiten sistemas PBX de terceros. En [este blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)se anunció un plan de jubilación para la compatibilidad de terceros, y los clientes de este modelo de implementación pueden migrar a sus usuarios a uno de los servicios/plataformas de comunicaciones unificadas de Microsoft o adquirir un buzón de voz de terceros o una solución de operador automático para estos usuarios. La integración de faxes no es compatible con los servicios basados en la nube; los clientes deberán migrar a una solución de terceros.

### <a name="who-is-affected"></a>¿A quién afecta?

Los clientes que consumen cualquiera de las siguientes características del servicio en línea de mensajería unificada de Exchange se ven afectados:

- Servicio de buzón de voz
- Servicio de operador automático
- Servicio de cola de llamadas
- Integración de fax

> [!Note]
> Los clientes que usan cualquiera de los servidores de Exchange local con mensajería unificada no se ven afectados. 

Obtenga más información sobre la experiencia de usuario y administrador impacto en el impacto de la [experiencia del usuario](#user-experience-impact).

## <a name="migration-plan-overview"></a>Información general del plan de migración

Microsoft identificó diversas implementaciones de clientes que consumen características de ExchUMO y estarán ayudando a los clientes a migrar basándose en el siguiente plan. 

|Grupo de clientes |Escala  |Detalles  |
|---------|---------|---------|
|Clientes que están listos para migrar<br><br>Características que se van a migrar:<br><ul><li>Correo de voz</ul>   |   Marzo: 2019 de mayo  |Acerca<ul><li>    Clientes con una sencilla implementación y uso del buzón de voz<li>Clientes que tienen todos los requisitos establecidos para que Microsoft ejecute la migración<ul>|
|Clientes con requisitos previos<br><br>Características que se van a migrar:<br><ul><li>Correo de voz<li>Operador automático<li>Cola de llamadas</ul> |  Mayo, 2019 de diciembre |Acerca <br><ul><li>La configuración híbrida no está completa<li>Los números de RTC híbridos no están configurados</ul>|
|Clientes que requieren la implicación del administrador & inversión en el cliente<br><br>Características que se van a migrar:<ul><li>Telefónica<li>Operador automático<li>Colas de llamadas<li>Integración de fax</ul>| Por 2020 de febrero  | Acerca <br><ul><li>El servicio ExchUMO está consumido por PBX de terceros<li>Clientes con requisitos de acceso de suscriptor de RTC<li>Clientes de SFB 2010 (no admitido)<li>Integración de fax</ul> |

## <a name="migration-steps"></a>Pasos de la migración

1.  **Obtener información**
 
    Familiarícese con el [anuncio del blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) y este artículo para planear una migración sin problemas para los usuarios. Consulte [comprobar el buzón de voz y las opciones de Skype empresarial](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) para obtener más información sobre las características del buzón de voz del sistema.  
 
2.  **Establecer una topología híbrida de Skype empresarial**

    Si no tiene establecida una topología híbrida de Skype empresarial, debe hacerlo para permitir una migración fluida de los usuarios del buzón de voz. Consulte [configurar la implementación híbrida de Skype empresarial](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) para obtener más información. 

    > [!Note]
    > No es necesario migrar los usuarios a conectados para la migración del servicio de correo de voz. Sin embargo, para que los usuarios locales aprovechen el servicio de buzón de voz del sistema telefónico, debe establecerse una topología híbrida.

3. **Planear la migración de los operadores automáticos**
    
    Los administradores pueden empezar a migrar sus operadores automáticos de ExchUMO al operador automático de la nube en cualquier momento. Consulte [configurar un operador automático de la nube](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) para obtener más información. Microsoft continúa proporcionando capacidades de operador automático adicionales que los clientes pueden considerar necesarios para su migración, los administradores deben evaluar el conjunto de características y migrar sus instancias de operador automático según corresponda. Para comparar la lista de características, consulte la matriz de características de los [servicios basados en la nube de ExchUMO y Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planear las pruebas y la validación posterior a la migración del buzón de voz**

    La migración del buzón de voz está controlada por Microsoft. No es necesario que los administradores hagan nada, dado que se establece la topología híbrida de requisitos previos. Microsoft realiza la validación y las pruebas necesarias para asegurarse de que la migración del buzón de voz de los usuarios no se interrumpa. Se recomienda a los administradores realizar pruebas y validaciones en su lado. Consulte [plan de pruebas sugerido y validación posterior a la migración para los administradores](#suggested-test-plan-and-post-migration-validation-for-admins) de un plan de pruebas recomendado. 

    > [!Note]
    > Lync Server 2010 no se admite. Si está en una implementación de servidor de 2010, debe planear una actualización de servidor o considere la posibilidad de migrar los usuarios a Microsoft Teams o Skype empresarial online.  

5. **Supervisar el centro de notificaciones de administrador**

    Busque un aviso en el centro de notificaciones del administrador con más detalles y escala de tiempo en relación con la migración de los usuarios. Las notificaciones se envían al menos 30 días antes del período de migración. 

    > [!Note]
    > Si recibió una notificación con la escala de tiempo de la migración de los usuarios y desea posponer la migración por un motivo importante para la empresa, puede hacerlo poniéndose en contacto con el soporte técnico de Microsoft. Tenga en cuenta que no puede posponer la migración más allá de la fecha de retiro, 2020 de febrero. Para los clientes que pueden tener más preguntas, comuníquese con su equipo de cuenta o con el soporte técnico de Microsoft. Los clientes que ya usan Office 365 pueden enviar un caso de soporte técnico a través del portal de administración de Office 365. 

6. **Considere la posibilidad de optar por una migración planeada**

    Puede optar por una migración de servicio de buzón de voz planificada a CVM. Antes de optar por, revise los detalles de este artículo, especialmente las secciones siguientes:

    - Pasos de la migración (esta sección)
    - Matriz de características de los servicios basados en la nube de ExchUMO y Azure
    - Impacto de la experiencia del usuario

    Al elegir una migración administrada, no recibirá una notificación de 30 días antes de la migración en el centro de mensajes del portal de administración de Microsoft 365.
 
    Para participar en una migración planeada, envíe una solicitud de correo electrónico desde la dirección de correo electrónico del administrador a [CVM@microsoft.com](mailto:cvm@microsoft.com) con la siguiente información:

    - Fecha preferida (martes): las ondas de migración se ejecutan todos los martes. Selecciona una fecha del martes que no esté más allá del 12/3/2019.
 
    - IDENTIFICADOR de inquilino: 32 caracteres del número en este formato 0046728c-688a-4472-a38f-098fec60ac6x. Puede encontrar su identificador de inquilino en el portal de administración de Microsoft 365 en Azure AD o mediante el siguiente cmdlet de PowerShell:`Get-CsTenant | Select ObjectId`
 
    Una vez que se haya migrado correctamente el inquilino, recibirá una confirmación por correo electrónico. 

## <a name="appendix"></a>Apéndice

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matriz de características de los servicios basados en la nube de ExchUMO y Azure

| Service | Nivel de característica | Característica | Notas  | VM en la nube/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| MEDIO  | Características del servicio| Admitir PBX de terceros    | Incluye todas las características proporcionadas a PBX de terceros, como MWI (indicador de mensaje en espera) con mensajes de notificación SIP de la mensajería instantánea en línea de Exchange | N   | Y    |
| MEDIO | Características del servicio  | Compatibilidad con Skype empresarial Server   |  | S | S    |
| MEDIO | Características del servicio | Soporte técnico de Microsoft Teams|  | Y | N    |
| MEDIO | Características del servicio | eDiscovery y retención  | Para la seguridad y el cumplimiento  | S | S    |
| MEDIO | Características del servicio | Compatibilidad con las reglas de Exchange | Para la seguridad y el cumplimiento  | S | S    |
| MEDIO | Características de usuario | Acceso telefónico RTC  | Acceso de suscriptor  | N | Y    |
| MEDIO | Características de usuario | Outlook Voice Access de RTC   | Acceso de suscriptor  | N | Y    |
| MEDIO | Características de usuario | Acceso telefónico con un punto de conexión autenticado | Llamar al servicio de buzón de voz para escuchar mensajes de voz y cambiar la configuración del buzón de voz| S | S    |
| MEDIO | Características de usuario | Configuración de usuario para deshabilitar el buzón de voz   |  | S | S    |
| MEDIO | Características de usuario | Configuración de usuario para cambiar el saludo personal  |  | S | S    |
| MEDIO | Características de usuario | Configuración de usuario para crear un saludo de OOF  |  | S | S    |
| MEDIO | Características de usuario | Configuración de usuario para cambiar el idioma predeterminado  |  | S | S    |
| MEDIO | Características de usuario | Configuración de usuario para sobrescribir el saludo predeterminado con TTS  |  | Y | N    |
| MEDIO | Características de usuario | Grabar saludos personales (dispositivo autenticado) |  | S | S    |
| MEDIO | Características de usuario | Grabar saludos personales (RTC): reproducir en el teléfono |  | N | Y    |
| MEDIO | Características de usuario | Configuración de usuario para deshabilitar la transcripción |  | N | Y    |
| MEDIO | Características de usuario | Cripciones  |  | S | S    |
| MEDIO | Características de usuario | Buzón de voz visual en todos los puntos de conexión   | Con control de usuario para reproducir, eliminar, indicador de espera de mensaje y alternancia de estado, en todos los puntos de conexión compatibles  | S | S    |
| MEDIO | Características de usuario | Formato de archivo de audio MP3 en Outlook    |  | Y | S    |
| MEDIO | Características de usuario | Control de reproducción de velocidad variable |  | Y | S    |
| MEDIO | Características de usuario | Reenviar un mensaje de voz  | Reenviar un mensaje de voz recibido a otros usuarios | Y | S    |
| MEDIO | Características de usuario | Enviar un mensaje de voz a un grupo de usuarios  |Difusión del buzón de voz   | N | Y   |
| MEDIO | Características de usuario | Notificación del buzón de voz con SMS    | Los usuarios pueden recibir un SMS cuando tienen un mensaje de voz nuevo    | N | Y    |
| MEDIO | Características de usuario | Idiomas de saludo compatibles | Detalles aquí:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | S    |
| MEDIO | Características de usuario | Reglas de contestador automático |  | Y | S    |
| MEDIO | Características de usuario | Reproducir en el teléfono (RTC): para reproducir el mensaje | Llamarme en mi celda para escuchar el mensaje de voz  | N | Y    |
| MEDIO | Características de usuario | Reproducir en el teléfono (autenticación): mensaje para reproducir | Llamarme en mi dispositivo autenticado  | Y | S    |
| MEDIO | Características de usuario | Buzón compartido entre varios usuarios |  | Y | S    |
| MEDIO | Características de los autores de llamadas  | Experiencia de la persona que llama: buzón de voz protegido | La persona que llama puede elegir una opción para marcar un mensaje grabado como protegido| N | Y    |
| MEDIO | Características de los autores de llamadas  | Experiencia de la persona que llama: buzón de voz privado | La persona que llama puede elegir una opción para marcar un mensaje grabado como privado  | N | Y    |
| MEDIO | Características de los autores de llamadas  | Detección de silencio   |  | N | Y    |
| MEDIO | Espacio empresarial-características de administración | Buzón de voz protegido en el nivel de servidor    | Tenant-admin puede configurar una regla de nivel de servicio para marcar el buzón de voz como protegido. | Y | S    |
| MEDIO | Espacio empresarial-características de administración | Límite de tiempo de duración de grabación  |     | Y | S    |
| MEDIO | Espacio empresarial-características de administración | Cambiar el tiempo de espera de detección de silencio    |  | N/D    | Y    |
| MEDIO | Espacio empresarial-características de administración | Cambiar número de error de entrada | CVM: codificado en 3 | N | Y    |
| MEDIO | Espacio empresarial-características de administración | Cambiar el idioma predeterminado |  | Y | S    |
| MEDIO | Espacio empresarial-características de administración | Deshabilitar/habilitar transcripción |  | S | S    |
| MEDIO | Espacio empresarial-características de administración | Deshabilitar o habilitar la notificación de llamada perdida |  | N | Y    |
| MEDIO | Espacio empresarial-características de administración | Ayudar a Microsoft a mejorar la vista previa del correo de voz    |  | S | S    |
| MEDIO | Espacio empresarial-características de administración | Personalizar mensaje de texto para usuarios habilitados|  | N/D    | Y    |
| MEDIO | Espacio empresarial-características de administración | Máscara de blasfemias de transcripción|  | Y | N    |
| MEDIO | Espacio empresarial-características de administración | Directiva de buzón de voz    |   | S | S    |
| MEDIO | Espacio empresarial-características de administración | Administración de portal web   |  | CY19   | Y    |
| MEDIO | Espacio empresarial-características de administración | PowerShell   |  | S | S    |
| AA | Características del servicio | AA compatibilidad con PBX de terceros    |  | N | Y    |
| AA | Características del servicio | Compatibilidad con Skype empresarial Server   |  | S | S    |
| AA | Características del servicio | Soporte técnico de Microsoft Teams|  | Y | N    |
| AA | Características del servicio | Marcado por nombre, entrada DTMF    |  | S | S    |
| AA | Características del servicio | Marcado por nombre, entrada de voz  |  | S | S    |
| AA | Características del servicio | Compatibilidad con varios idiomas | Detalles del idioma aquí:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | S | S    |
| AA | Características del servicio | Transferir al operador, CQ o un usuario |  | S | S    |
| AA | Características del servicio | Transferir al número RTC internamente (RNL)  |  | S | S    |
| AA | Características del servicio | Transferir a un número RTC externamente  |  | Consultar la sección problemas conocidos a continuación | Y    |
| AA | Características del servicio | Horario comercial |  | S | S    |
| AA | Características del servicio | Opciones de menú | Opciones del menú de IVR  | S | S    |
| AA | Características del servicio | Asignación de un número de RTC en la nube a AA |  | Y | N    |
| AA | Características del servicio | Asignación de un número de RTC local a AA  |  | S | S    |
| AA | Características del servicio | Selección personalizada de usuarios  | Permitir que los autores de llamadas adquieran una lista personalizada de usuarios de la organización| S | S    |
| AA | Características del servicio | Tratamiento fuera de horario laboral y festivo  |  | S | S    |
| AA | Características del servicio | Saludo personalizado con texto a voz  |  | S | S    |
| AA | Características del servicio | Marcado de extensión   | Contactar con un usuario marcando su extensión  | CY19   | Y    |
| AA | Características del servicio | Buzón para que las personas que llaman a un AA dejen un mensaje    |  | CY19   | Y    |
| AA | Características del servicio | Varias asignaciones de números RTC a un AA|  | S | S    |
| AA | Espacio empresarial-características de administración | Administración de portal web   |  | Y | N    |
| AA | Espacio empresarial-características de administración | Cmdlets de PowerShell  |  | S | S    |
| Fax| Características del servicio | Integración de fax|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de prueba sugerido y validación posterior a la migración para administradores

Para comprobar que los usuarios se han migrado al buzón de voz de la nube, deje un mensaje de voz a un usuario y compruebe el cuerpo del mensaje en Outlook.  Los mensajes de voz en la nube tienen un pie de página que dice:

**Gracias por usar transcripción. Si no ve una transcripción anteriormente, se debe a que la calidad del audio no es lo suficientemente clara para transcribir.**

Cuando pruebe la funcionalidad de buzón de voz una vez que los usuarios hayan migrado, asegúrese de tener en cuenta los siguientes escenarios:

- Validar el acceso al buzón de voz en todos los tipos de extremos de su organización: aplicaciones y teléfonos IP. 
- Validar con usuarios de muestra que se reproducen los saludos personalizados configurados para las personas que llaman.   
- Si su organización tiene un requisito legal o de cumplimiento para deshabilitar la transcripción para los usuarios, asegúrese de que está deshabilitada después de la migración. Para obtener más información, consulte [configurar el buzón de voz en la nube](/microsoftteams/set-up-phone-system-voicemail).
- Si ha configurado previamente directivas y reglas de la máquina virtual de Exchange, asegúrese de que son eficaces.
- Familiarícese con los cmdlets de PowerShell del servicio de buzón de voz en la nube para cambiar la configuración de usuario.  

### <a name="user-experience-impact"></a>Impacto de la experiencia del usuario

A continuación se resumen la experiencia de migración del buzón de voz de usuario final.


|Ejecución  |Cambio en la experiencia del usuario|
|---------|---------|
|Notificación de correo electrónico | Sin cambios<br>No se envía correo electrónico a los usuarios para notificarles la activación o la migración de la cuenta de correo de voz. |
|Acceso a mensajes anteriores | Sin cambios<br>Los usuarios tienen acceso a sus mensajes de voz anteriores en todos los puntos de conexión admitidos. |
|Recibir una VM en Outlook, aplicaciones de SFB| Sin cambios<br>Los usuarios continúan recibiendo sus mensajes de voz en todos los puntos de conexión admitidos. |
|Cripciones | Avanzado<br>La transcripción de CVM tiene una tasa de precisión muy superior e idiomas admitidos que ExchUMO. |
|Configuración de usuario | Nueva experiencia<br>Los usuarios pueden cambiar sus preferencias desde un portal de configuración de usuario (USP). Los usuarios pueden acceder a su USP desde un hipervínculo en el correo electrónico del buzón de voz, o el botón Configuración del usuario en su cliente de SFB. https://aka.ms/vmsettings.   
 |Características| Para obtener más información, consulta la comparación de conjuntos de características. |
|Reglas de Outlook para mensajes de VM | Sin cambios<br>Las reglas creadas previamente se aplicarán a los mensajes de CVM después de la migración.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Administración y aprovisionamiento de usuarios en CVM 

Los nuevos usuarios de Skype empresarial se aprovisionarán automáticamente para el buzón de voz de nube cuando se creen. No se necesita ninguna licencia o trabajo de administración adicional para aprovisionar nuevos usuarios del buzón de voz. Consulte [configurar el buzón de voz en la nube](/microsoftteams/set-up-phone-system-voicemail) para obtener información sobre la administración de directivas para usuarios existentes y nuevos.

#### <a name="admin-auto-attendant-management-experience"></a>Experiencia de administración de operadores automáticos de administrador 

Para obtener más información sobre los operadores automáticos, vea [configurar un operador automático de la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant.md). 

#### <a name="known-issues"></a>Problemas conocidos

**Transferencia automática del operador a RTC** Se recomienda a los clientes configurar una solución alternativa temporal para cumplir con los requisitos de transferencia de una llamada de operador automático a un número RTC externo o a una instancia de RGS. 
 
Se identificó un problema durante el control de calidad con la característica transferir a número RTC, que no se fijará en el tiempo para los clientes para empezar a migrar desde el servicio de Exchange UMO antes de la fecha de jubilación programada del 1 de febrero de 2020. Como solución alternativa, los administradores pueden transferir las personas que llaman al operador automático a un usuario virtual local con una configuración de desvío de llamada activa para el número de teléfono de RTC deseado o el número de teléfono RGS. 
 
Experiencia prevista
- Los administradores no necesitan conceder licencia al usuario virtual, ya que es una solución alternativa. 
- Los administradores pueden manipular la identificación de llamadas que el receptor de RTC verá asignando el número deseado al usuario virtual o usando las funciones de manipulación de dígitos de SBC 
- Las personas que llaman a la RTC no experimentarán ningún retraso durante la transferencia de llamadas y seguirán viendo la identificación de llamadas del operador automático después de que la transferencia se realice correctamente.  

**Buzón compartido:** Un buzón de correo compartido que se configura con Exchange UM online seguirá recibiendo mensajes después de migrarlos a CVM y seguirán siendo accesibles para los usuarios a través de Outlook. Sin embargo, el acceso para cambiar los mensajes de saludo de estos buzones no estará disponible una vez que se haya migrado a CVM. Los clientes con buzones compartidos que se usan para capturar las personas que llaman al operador automático deben aprovechar los operadores automáticos y las colas de llamadas capacidades de buzón de correo compartido una vez publicadas (ETA octubre de 2019).
  
**Actualizar a la pancarta de Teams en el cliente de SFB:** El servicio de CVM se basa en la infraestructura de Microsoft Teams; las llamadas a él desde un cliente de Skype empresarial pueden hacer que se muestre en el cliente un banner de información que diga: "el nombre de usuario no está usando Skype empresarial. Para obtener una experiencia más rica, cambie a teams o inicie una reunión de Skype.
Asegúrese de actualizar el cliente de Skype empresarial de los usuarios a la actualización de cliente de C2R más reciente para evitar que aparezca esta pancarta. 
  
**Configure el buzón de voz para que le lleve a OWA:** Al hacer clic en "configurar el correo de voz", el cliente seguirá teniendo clientes de Skype empresarial Server 2015/2013 en la página del portal de Office Web Access (OWA) después de la migración a CVM. Se ha quitado toda la configuración de la ficha buzón de voz en OWA y se mostrará un mensaje de bienvenida con un vínculo de redireccionamiento para llevar a los usuarios al portal de configuración de usuario de CVM. 
 
**Cambiar saludo de acceso móvil:** El acceso de suscriptor de RTC no se admite en CVM. Para los usuarios que tienen que cambiar su saludo de forma remota, se agrega una opción de menú "cambiar el saludo" al servicio de correo de voz para clientes móviles. Los usuarios pueden llamar a este servicio pulsando y manteniendo presionada la tecla "1" en el teclado de marcado de cliente móvil. 
