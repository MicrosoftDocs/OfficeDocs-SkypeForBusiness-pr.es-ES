---
title: Administrar las conferencias en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumen: Obtenga información sobre cómo administrar las conferencias en Skype para Business Server.'
ms.openlocfilehash: 683da834b6de82d9da857ad4ab0a07e2ac4a6731
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895128"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Administrar las conferencias en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo administrar las conferencias en Skype para Business Server.
  
En este tema se describe cómo administrar conferencias. Para obtener más información acerca de cómo planear e implementar una conferencia, vea [Plan para las conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencias en Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
En Skype para Business Server, se administran los detalles de conferencia mediante la especificación de configuración y la configuración de directiva de la siguiente manera. Tenga en cuenta que la conferencia de términos y la reunión se utilizan a veces indistintamente. Sin embargo, en general, puede pensar en una reunión como una instancia específica de la conferencia.
  
- **La configuración de directivas de conferencia** contiene una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, ancho de banda y aspectos jurídicos de las reuniones.
    
    Tenga en cuenta que las directivas de conferencia se aplican al usuario o sitio y no se pueden aplicar a una reunión determinada. Por lo tanto, se puede crear algunas semanas de antelación a la invitación a la reunión de la conferencia, pero debe aplicarse la directiva de conferencia restrictivo a Skype del organizador de la reunión para la cuenta de empresa justo antes de que se inicia la conferencia. 
    
    Si una cuenta dedicada se usa para el rol de organizador de la reunión, la directiva de conferencia puede permanecer asignada a esa cuenta. Si el organizador de la reunión usa un Skype general para la cuenta de empresa, se debe quitar la directiva una vez finalizada la conferencia.
    
- **Las opciones de configuración de reunión** definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones. Tenga en cuenta que estas opciones solo afectan a las reuniones programadas. La configuración de reunión se aplica por grupo, sitio o de forma global.
    
- Determinación de **la configuración de conferencia** elementos tales como el tamaño máximo permitido para el contenido de las reuniones y los documentos; cantidad máxima de ancho de banda para el servicio de conferencia de uso compartido de la aplicación; límites de almacenamiento y períodos de expiración; descargas de las direcciones URL internas y externas del cliente compatible; punteros a las direcciones URL internas y externas donde los usuarios pueden obtener ayuda de conferencia y recursos; y los puertos usados para el uso compartido de aplicaciones, audio de cliente, las transferencias de archivos y el tráfico de medios.
    
    Esta configuración le permite administrar los servidores reales. Sólo se pueden establecer estas opciones de configuración mediante el uso de Skype para Shell de administración de servidor empresarial. 
    
- **La configuración de acceso telefónico** le permite definir información acerca de cómo los usuarios pueden acceder por teléfono a una conferencia y si lo tienen permitido o no. Usted especifica alguna información de acceso telefónico, como el número de acceso, desde la pestaña Conferencias del Panel de control y alguna información de acceso telefónico, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC desde la pestaña Enrutamiento de voz del Panel de control.
    
- **La configuración de la directiva de PIN** le permite ponerle nombre al PIN y definir el PIN que usan los participantes para el acceso telefónico local.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Administrar las conferencias mediante Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial

Puede administrar la mayoría de las directivas de conferencia y opciones de configuración mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial. Algunas opciones de configuración están disponibles sólo mediante Skype para Shell de administración de servidor empresarial.
  
- Para administrar la configuración de la directiva de conferencia:
    
  - En el Panel de control, seleccione **Conferencias | Directiva de conferencias**.
    
  - En PowerShell, busque los cmdlets **-CsConferencingPolicy**.
    
- Para administrar la configuración de reuniones:
    
  - En el Panel de control, seleccione **Conferencias | Configuración de reuniones**.
    
  - En Skype para Shell de administración de servidor empresarial, de búsqueda de los cmdlets de **-CsMeetingConfiguration** .
    
- Para administrar la configuración de números de acceso telefónico local:
    
  - En el Panel de control, seleccione **Conferencias | Número de acceso telefónico**.
    
  - En Skype para Shell de administración de servidor empresarial, de búsqueda de los cmdlets de **-CsDialInConferencing** .
    
- Para administrar la información de acceso telefónico local, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC: 
    
  - En el Panel de control, seleccione **Conferencias | Enrutamiento de voz**.
    
  - En Skype para Shell de administración de servidor empresarial, busque los cmdlets **- CsDialPlan** y **- CsVoice** .
    
- Para administrar la configuración de la directiva de PIN:
    
  - En el Panel de control, seleccione **Conferencias | Directiva de PIN**.
    
  - En Skype para Shell de administración de servidor empresarial, de búsqueda de los cmdlets de **-CsPinPolicy** .
    
- Para administrar la configuración de conferencia, debe usar el Skype para Shell de administración de servidor empresarial. Busque los cmdlets **-CsConferencingConfiguration**.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype para los cmdlets del Shell de administración de servidor empresarial

Puede usar el siguiente Skype para los cmdlets del Shell de administración de servidor empresarial para administrar las conferencias: 
  
**Configuración de la directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que han sido configuradas para el uso en la organización. Las directivas de conferencia determinan las características y las capacidades que pueden usarse en una conferencia. Esto incluye desde si la conferencia puede incluir audio y vídeo IP hasta el máximo de personas que pueden asistir a una reunión.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
   
**Opciones de configuración de reuniones**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reunión en uso en la organización. Las opciones de configuración de reunión ayudan a definir el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en estas reuniones.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una recopilación de opciones de configuración de reunión en el ámbito del sitio o del servicio. Tenga en cuenta que esta configuración sólo afecta a las reuniones programadas; no afectan a las reuniones de ad-hoc creadas haciendo clic en la opción Reunirse ahora en Skype para la empresa.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
   
**Opciones de configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de la conferencia para la organización. La configuración de la conferencia determina aspectos como el tamaño máximo permitido para el contenido y los documentos de conferencia, el período de gracia del contenido (es decir, el tiempo durante el que se almacenará el contenido antes de eliminarlo) y las direcciones URL para las descargas internas y externas del cliente admitido.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de configuración de conferencias.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Quita la colección especificada de opciones de configuración de conferencia.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una colección existente de opciones de configuración de conferencias.  <br/> |
   
**Opciones de configuración de conferencia de acceso telefónico local**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Devuelve información sobre los directorios de conferencia configurados en su organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información acerca de cómo Skype para Business Server responde cuando los usuarios se unen o abandonan una conferencia de acceso telefónico.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local que estén configurados para el uso en la organización La conferencia de acceso telefónico permite a los usuarios utilizar un teléfono móvil "normal", o un dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia en línea.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) que se usa para las conferencias de acceso telefónico local. DTMF permite a los usuarios que participan por teléfono en una conferencia controlar la configuración de la conferencia (por ejemplo, activar y desactivar el audio o bloquear y desbloquear la conferencia) con el teclado numérico del teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas de configuración regional/minoritarios, compatibles para su uso con Skype para Business Server marcado en las conferencias. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa los directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype para Business Server. Esto ayuda a proporcionar la interoperabilidad entre Skype para Business Server y Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre la conferencia.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Esta configuración determina cómo Skype para Business Server responde cuando los usuarios se unen o abandonan una conferencia de acceso telefónico. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nueva recopilación de configuraciones de señalización tono de marcado de frecuencia múltiple (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre las conferencias.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Esta configuración determina cómo Skype para Business Server responde cuando los usuarios se unen o abandonan una conferencia de acceso telefónico.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico local. La conferencia de acceso telefónico local permite a los usuarios usar un teléfono "normal", móvil u otro dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica la configuración que determina cómo Skype para Business Server responde cuando los usuarios se unen o abandonan una conferencia de acceso telefónico.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de la directiva de PIN**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. Autenticación de PIN permite a los usuarios obtener acceso a Skype para Business Server proporcionando un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal (PIN) de cliente.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o varias directivas de número de identificación personal (PIN) de cliente.  <br/> |
   
**Otra configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deshabilita un Skype para salas de reuniones de Business Server. Una sala de reuniones es un dispositivo de conferencias diseñado para abordar escenarios de colaboración y videoconferencia en pequeñas salas de reuniones. Al deshabilitar una sala de reuniones de objetos quitar todas las Skype para los atributos específicos del servidor empresarial Active Directory asignada a la cuenta de usuario que representa la sala de reuniones. Sin embargo, no se elimina la cuenta de usuario de Active Directory propio.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Permite un Skype para salas de reuniones de Business Server. Para habilitar una sala de reuniones, primero debe crear una cuenta de usuario de Active Directory que representará ese sistema. Tenga en cuenta que, aunque los objetos de la sala de reuniones se basan en las cuentas de usuario, estos objetos no se mostrarán al ejecutar el cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Devuelve información sobre el aviso de declinación de responsabilidades de conferencias usado en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, los usuarios que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Devuelve información acerca de todas las Skype para Business Server configuradas para su uso en la organización de salas de reuniones.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Mueve un Skype para Business Server objeto de sala de un grupo de registrador a otro de la reunión.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Borra el texto del encabezado y el cuerpo de la declinación de responsabilidades de conferencias usada en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, los usuarios que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica los valores de propiedad de un Skype para salas de reuniones de Business Server existente.  <br/> |
   
**Probar la configuración**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de uso compartido de aplicaciones.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Realiza una prueba para ver si un usuario puede conectar con el proveedor de servicios de audioconferencia. Estos proveedores son organizaciones de terceros que suministran servicios de audioconferencia a organizaciones. Entre otras cosas, los proveedores de audioconferencia permiten a los usuarios que no se encuentran en la oficina, y que no están conectados a la red corporativa o Internet, participar en la parte de audio de una conferencia o una reunión.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de audio o vídeo (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Comprueba si un par de los usuarios puede participar en una Skype para conferencia web de Business Server que incluye las actividades, como el uso compartido o ver diapositivas de PowerPoint, pizarras o sondeos. El cmdlet también comprueba que la Skype para el servicio de conferencias web de Business Server puede detectar Office Web Apps Server y que un cliente puede cargar un archivo de PowerPoint para difusión mediante Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Comprueba si un usuario puede participar en una sesión de conferencia de acceso telefónico local.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Prueba un número de teléfono con un plan de marcado (antes denominado perfil de ubicación) y devuelve la regla de normalización que se aplicará al número, así como el número traducido después de haber aplicado la regla de normalización.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Comprueba la capacidad de los tres usuarios para participar en una Skype para conferencia de servicio de movilidad de Business Server. El servicio de movilidad permite a los usuarios de teléfonos móviles como iPhone y los teléfonos de Windows para realizar operaciones tales como los mensajes instantáneos de exchange y la información de presencia; almacenar y recuperar el correo de voz internamente en lugar de con su proveedor de telefonía móvil; y sacar partido de Skype para las capacidades de Business Server como vía trabajo y conferencias de acceso telefónico de salida.  <br/> **Nota:** Los clientes que usan MCX no se admiten en Skype para Business Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios de programar y dirigir una conferencia en línea, y participar en ella, con la API web de comunicaciones unificadas (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Devuelve información de diagnóstico para las funciones de conferencia de datos incluidos en Skype para Business Server.  <br/> |
   

