---
title: Administrar conferencias en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumen: Conozca cómo administrar conferencias en Skype para Business Server 2015.'
ms.openlocfilehash: 2239c5aae8754e381bf6cf7b8b41aa6ef31b8033
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-in-skype-for-business-server-2015"></a>Administrar conferencias en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar conferencias en Skype para Business Server 2015.
  
En este tema se describe cómo administrar conferencias. Para obtener más información acerca de cómo planear e implementar la conferencia, consulte [Plan de conferencia en Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) y [conferencias de implementar en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
En Skype para Business Server, se administran los detalles de la conferencia mediante la especificación de configuración de directivas y la configuración como sigue. Tenga en cuenta que la reunión y conferencia de términos se utilizan a veces indistintamente. Pero, en general, piensa que una reunión como una instancia específica de la conferencia.
  
- **La configuración de directivas de conferencia** contiene una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, ancho de banda y aspectos jurídicos de las reuniones.
    
    Tenga en cuenta que las directivas de conferencia se aplican al usuario o sitio y no se pueden aplicar a una reunión determinada. Por lo tanto, se puede crear algunas semanas de antelación a la invitación a la reunión de la conferencia, pero la directiva restrictiva conferencia debe aplicarse al Skype del organizador de la reunión para la cuenta de empresa antes de que inicie la conferencia. 
    
    Si una cuenta dedicada se usa para el rol de organizador de la reunión, la directiva de conferencia puede permanecer asignada a esa cuenta. Si el organizador de la reunión utiliza un Skype general para la cuenta de empresa, la directiva debe quitarse una vez finalizada la conferencia.
    
- **Las opciones de configuración de reunión** definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones. Tenga en cuenta que estas opciones solo afectan a las reuniones programadas. La configuración de reunión se aplica por grupo, sitio o de forma global.
    
- **Configuración de conferencia** determinan cuestiones como el tamaño máximo permitido para el contenido de la reunión y los documentos; cantidad máxima de ancho de banda para el servicio de conferencia de uso compartido de aplicaciones; límites de almacenamiento y los períodos de vencimiento; las direcciones URL internas y externas de descargas de cliente admitido; punteros a las direcciones URL internas y externas donde los usuarios pueden obtener ayuda de conferencia y recursos; y los puertos utilizados para compartir aplicaciones, audio del cliente, las transferencias de archivos y tráfico de medios.
    
    Estas opciones permiten administrar los servidores reales. Esta configuración sólo puede establecerse mediante el uso de Skype para el Shell de administración de servidor empresarial. 
    
- **La configuración de acceso telefónico** le permite definir información acerca de cómo los usuarios pueden acceder por teléfono a una conferencia y si lo tienen permitido o no. Usted especifica alguna información de acceso telefónico, como el número de acceso, desde la pestaña Conferencias del Panel de control y alguna información de acceso telefónico, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC desde la pestaña Enrutamiento de voz del Panel de control.
    
- **La configuración de la directiva de PIN** le permite ponerle nombre al PIN y definir el PIN que usan los participantes para el acceso telefónico local.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Administrar conferencias utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial

Puede administrar más directivas de conferencia y opciones de configuración utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial. Algunas opciones de configuración están disponibles sólo mediante Skype para el Shell de administración de servidor de empresa.
  
- Para administrar la configuración de la directiva de conferencia:
    
  - En el Panel de control, seleccione **Conferencias | Directiva de conferencias**.
    
  - En PowerShell, busque los cmdlets **-CsConferencingPolicy**.
    
- Para administrar la configuración de reuniones:
    
  - En el Panel de control, seleccione **Conferencias | Configuración de reuniones**.
    
  - En Skype para el Shell de administración de servidor empresarial, buscar los cmdlets **- CsMeetingConfiguration** .
    
- Para administrar la configuración de números de acceso telefónico local:
    
  - En el Panel de control, seleccione **Conferencias | Número de acceso telefónico**.
    
  - En Skype para el Shell de administración de servidor empresarial, buscar los cmdlets **- CsDialInConferencing** .
    
- Para administrar la información de acceso telefónico local, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC: 
    
  - En el Panel de control, seleccione **Conferencias | Enrutamiento de voz**.
    
  - En Skype para el Shell de administración de servidor empresarial, buscar los cmdlets **- CsDialPlan** y **- CsVoice** .
    
- Para administrar la configuración de la directiva de PIN:
    
  - En el Panel de control, seleccione **Conferencias | Directiva de PIN**.
    
  - En Skype para el Shell de administración de servidor empresarial, buscar los cmdlets **- CsPinPolicy** .
    
- Para administrar la configuración de la conferencia, debe utilizar el Skype para el Shell de administración de servidor de empresa. Busque los cmdlets **-CsConferencingConfiguration**.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype para los cmdlets del Shell de administración de servidor de Business

Puede utilizar el siguiente Skype para los cmdlets del Shell de administración de servidor de Business para administrar la conferencia: 
  
**Configuración de la directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que han sido configuradas para el uso en la organización. Las directivas de conferencia determinan las características y las capacidades que pueden usarse en una conferencia. Esto incluye desde si la conferencia puede incluir audio y vídeo IP hasta el máximo de personas que pueden asistir a una reunión.  <br/> |
|[Concesión CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[Nueva CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Quitar CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Conjunto de CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
   
**Opciones de configuración de la reunión**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reunión en uso en la organización. Las opciones de configuración de reunión ayudan a definir el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en estas reuniones.  <br/> |
|[Nueva CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de reunión en el ámbito de sitio o de servicio. Tenga en cuenta que esta configuración sólo afecta a las reuniones programadas; no afectan a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en Skype para el negocio.  <br/> |
|[Quitar CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Conjunto de CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
   
**Configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de la conferencia para la organización. La configuración de la conferencia determina aspectos como el tamaño máximo permitido para el contenido y los documentos de conferencia, el período de gracia del contenido (es decir, el tiempo durante el que se almacenará el contenido antes de eliminarlo) y las direcciones URL para las descargas internas y externas del cliente admitido.  <br/> |
|[Nueva CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de configuración de conferencias.  <br/> |
|[Quitar CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Quita la colección especificada de opciones de configuración de conferencia.  <br/> |
|[Conjunto de CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una colección existente de opciones de configuración de conferencias.  <br/> |
   
**Opciones de configuración de acceso telefónico**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Devuelve información sobre los directorios de conferencia configurados en su organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información acerca de cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local que estén configurados para el uso en la organización La conferencia de acceso telefónico permite a los usuarios utilizar un teléfono móvil "normal", o un dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia en línea.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) que se usa para las conferencias de acceso telefónico local. DTMF permite a los usuarios que participan por teléfono en una conferencia controlar la configuración de la conferencia (por ejemplo, activar y desactivar el audio o bloquear y desbloquear la conferencia) con el teclado numérico del teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas regionales o minoritarios, compatibles con Skype para Business Server marcado en conferencias. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Concesión CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[CsLegacyConferenceDirectory de importación](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype para Business Server. Esto ayuda a proporcionar interoperabilidad entre Skype para Business Server y Office Communications Server 2007 R2.  <br/> |
|[Mover CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre la conferencia.  <br/> |
|[Nueva CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Nueva CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[Nueva CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Estos ajustes determinan cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[Nueva CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nueva recopilación de configuraciones de señalización tono de marcado de frecuencia múltiple (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[Nueva CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Quitar CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre las conferencias.  <br/> |
|[Quitar CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Quitar CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Estos ajustes determinan cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico.  <br/> |
|[Quitar CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Conjunto de CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico local. La conferencia de acceso telefónico local permite a los usuarios usar un teléfono "normal", móvil u otro dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia.  <br/> |
|[Conjunto de CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica opciones que determinan cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico.  <br/> |
|[Conjunto de CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Conjunto de CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de la directiva de NIP**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. Autenticación de PIN permite a los usuarios acceder a Skype para Business Server con un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Concesión CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[Nueva CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal (PIN) de cliente.  <br/> |
|[Quitar CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Conjunto de CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o varias directivas de número de identificación personal (PIN) de cliente.  <br/> |
   
**Otras opciones de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Deshabilitar CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deshabilita un Skype para salas de reuniones de Business Server. Una sala de reuniones es un dispositivo de conferencias diseñado para desarrollar videoconferencias y escenarios de colaboración en salas de conferencias pequeñas. Al deshabilitar una sala de reuniones objeto quitar todos lo Skype para atributos específicos del negocio servidor Active Directory asignada a la cuenta de usuario que representa la sala de reuniones. Sin embargo, no se elimina la cuenta de usuario de Active Directory propio.  <br/> |
|[Habilitar CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Permite un Skype para salas de reuniones de Business Server. Para habilitar una sala de reuniones, primero debe crear una cuenta de usuario de Active Directory que representará ese sistema. Tenga en cuenta que, aunque los objetos de la sala de reuniones se basan en las cuentas de usuario, estos objetos no se mostrarán al ejecutar el cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Devuelve información sobre el aviso de declinación de responsabilidades de conferencias usado en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, los usuarios que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Devuelve información sobre todos lo Skype para Business Server configurados para su uso en la organización de salas de reuniones.  <br/> |
|[Mover CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Mueve un Skype para Business Server reunión objeto de sala de grupo de un registrador a otro.  <br/> |
|[Quitar CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Borra el texto del encabezado y el cuerpo de la declinación de responsabilidades de conferencias usada en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, los usuarios que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Conjunto de CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica los valores de propiedad de un Skype para la sala de reuniones de Business Server existente.  <br/> |
   
**Probar la configuración**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[CsASConference de prueba](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de uso compartido de aplicaciones.  <br/> |
|[CsAudioConferencingProvider de prueba](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Realiza una prueba para ver si un usuario puede conectar con el proveedor de servicios de audioconferencia. Estos proveedores son organizaciones de terceros que suministran servicios de audioconferencia a organizaciones. Entre otras cosas, los proveedores de audioconferencia permiten a los usuarios que no se encuentran en la oficina, y que no están conectados a la red corporativa o Internet, participar en la parte de audio de una conferencia o una reunión.  <br/> |
|[CsAVConference de prueba](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de audio o vídeo (A/V).  <br/> |
|[CsDataConference de prueba](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Comprueba si es o no un par de usuarios puede participar en un Skype para conferencia web Business Server incluye actividades como compartir o ver diapositivas de PowerPoint, pizarras o las encuestas. El cmdlet también comprueba que el Skype para el servicio de conferencias web Business Server puede detectar el servidor de Office Web Apps y que un cliente puede cargar un archivo de PowerPoint para difusión por servidor de Office Web Apps.  <br/> |
|[CsDialInConferencing de prueba](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Comprueba si un usuario puede participar en una sesión de conferencia de acceso telefónico local.  <br/> |
|[CsDialPlan de prueba](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Prueba un número de teléfono con un plan de marcado (antes denominado perfil de ubicación) y devuelve la regla de normalización que se aplicará al número, así como el número traducido después de haber aplicado la regla de normalización.  <br/> |
|[CsMcxConference de prueba](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Comprueba la capacidad de tres usuarios para participar en un Skype para conferencia de servicio de movilidad Business Server. El servicio de movilidad permite a los usuarios de teléfonos móviles como iPhone y los teléfonos de Windows para realizar operaciones tales como intercambiar mensajes instantáneos e información de presencia; almacenar y recuperar el correo de voz internamente, en lugar de con su proveedor de telefonía móvil; y aprovechar las ventajas de Skype para capacidades de Business Server como una llamada a través de trabajo y conferencias de acceso telefónico de salida.  <br/> |
|[CsUcwaConference de prueba](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios de programar y dirigir una conferencia en línea, y participar en ella, con la API web de comunicaciones unificadas (UCWA).  <br/> |
|[Depuración CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Devuelve información de diagnóstico para las capacidades de conferencia de datos incluidos en Skype para Business Server.  <br/> |
   

