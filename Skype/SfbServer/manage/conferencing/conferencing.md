---
title: Administrar conferencias en Skype Empresarial Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumen: obtenga información sobre cómo administrar conferencias en Skype Empresarial Server.'
---

# <a name="manage-conferencing-in-skype-for-business-server"></a>Administrar conferencias en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar conferencias en Skype Empresarial Server.
  
En este tema se describe cómo administrar conferencias. Para obtener más información sobre cómo planear e implementar conferencias, vea [Plan for conferencing in Skype Empresarial Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
En Skype Empresarial Server, puede administrar los detalles de las conferencias especificando la configuración y la configuración de la siguiente manera. Tenga en cuenta que los términos conferencia y reunión a veces se usan indistintamente. Pero, en general, puede pensar en una reunión como una instancia específica de conferencia.
  
- **La configuración de** directiva de conferencia abarca una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir. Puede usar directivas de conferencia para administrar aspectos de seguridad, ancho de banda y legales de las reuniones.
    
    Tenga en cuenta que las directivas de conferencia se aplican al usuario o al sitio y no se pueden aplicar a una reunión específica. Por lo tanto, la invitación a la reunión para la conferencia se puede crear con algunas semanas de antelación, pero la directiva de conferencia restrictiva debe aplicarse a la cuenta de Skype Empresarial del organizador de la reunión justo antes de que comience la conferencia. 
    
    Si se usa una cuenta dedicada para el rol Organizador de reuniones, la directiva de conferencia puede permanecer asignada a esa cuenta. Si el organizador de la reunión usa una cuenta Skype Empresarial general, la directiva debe quitarse una vez finalizada la conferencia.
    
- **Las opciones de** configuración de reunión determinan el tipo de reuniones que los usuarios pueden crear, además de controlar cómo (o incluso si) los usuarios anónimos y los usuarios de conferencias de acceso telefónico local pueden unirse a estas reuniones. Tenga en cuenta que esta configuración solo afecta a las reuniones programadas. Las configuraciones de reunión se aplican por grupo, por sitio o globalmente.
    
- **Las opciones de configuración de conferencia** determinan aspectos como el tamaño máximo permitido para contenido y entregas de reuniones; cantidad máxima de ancho de banda para el servicio de conferencia de uso compartido de aplicaciones; límites de almacenamiento y períodos de expiración; las direcciones URL de las descargas internas y externas del cliente admitido; punteros a direcciones URL internas y externas donde los usuarios pueden obtener recursos y ayuda para conferencias; y los puertos usados para el uso compartido de aplicaciones, el audio del cliente, las transferencias de archivos y el tráfico multimedia.
    
    Esta configuración le permite administrar los propios servidores reales. Esta configuración solo se puede establecer mediante Skype Empresarial Server Shell de administración. 
    
- **La configuración de acceso telefónico** le permite definir información acerca de si los usuarios acceden desde un teléfono y cómo lo hace. Se especifica parte de la información de acceso telefónico local, como el número de acceso, desde la pestaña Conferencia del Panel de control y cierta información de acceso telefónico local (como el plan de marcado, la directiva de voz, la ruta y el uso de RTC) desde la pestaña Enrutamiento de voz del Panel de control.
    
- **La configuración de directiva de PIN** permite nombrar y definir el PIN que los participantes usan para el acceso telefónico local.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Administrar conferencias con el Panel de control Skype Empresarial Server o mediante el Shell Skype Empresarial Server administración

Puede administrar la mayoría de las directivas de conferencia y las opciones de configuración mediante Skype Empresarial Server Panel de control o mediante Skype Empresarial Server Shell de administración. Algunas opciones de configuración solo están disponibles mediante Skype Empresarial Server Shell de administración.
  
- Para administrar la configuración de directiva de conferencia:
    
  - En el Panel de control, seleccione **Conferencia | Directiva de conferencia**.
    
  - En PowerShell, busque los **cmdlets -CsConferencingPolicy** .
    
- Para administrar las opciones de configuración de reunión:
    
  - En el Panel de control, seleccione **Conferencia | Configuración de la reunión**.
    
  - En Skype Empresarial Server Shell de administración, busque los **cmdlets -CsMeetingConfiguration**.
    
- Para administrar la configuración del número de acceso telefónico:
    
  - En el Panel de control, seleccione **Conferencia | Número de acceso telefónico.**
    
  - En Skype Empresarial Server Shell de administración, busque los **cmdlets -CsDialInConferencing**.
    
- Para administrar la información de acceso telefónico local, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC: 
    
  - En el Panel de control, seleccione **Conferencia | Enrutamiento de voz**.
    
  - En Skype Empresarial Server Shell de administración, busque los **cmdlets -CsDialPlan** y **-CsVoice**.
    
- Para administrar la configuración de directiva de PIN:
    
  - En el Panel de control, seleccione **Conferencia | Directiva de PIN**.
    
  - En Skype Empresarial Server Shell de administración, busque los **cmdlets -CsPinPolicy**.
    
- Para administrar las opciones de configuración de conferencia, debe usar el Shell Skype Empresarial Server administración. Busque **cmdlets -CsConferencingConfiguration** .
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype Empresarial Server cmdlets del Shell de administración

Puede usar los siguientes cmdlets Skype Empresarial Server Shell de administración para administrar conferencias: 
  
**Configuración de directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización. Las directivas de conferencia determinan las características y prestaciones que se pueden usar en una conferencia; esto incluye cualquier cosa desde si la conferencia puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir a una reunión.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
   
**Opciones de configuración de reuniones**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reunión que se usan actualmente en la organización. Las opciones de configuración de reuniones ayudan a determinar el tipo de reuniones que los usuarios pueden crear y a controlar cómo (o incluso si) los usuarios anónimos y los usuarios de conferencias de acceso telefónico local pueden unirse a estas reuniones.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una recopilación de opciones de configuración de reunión en el ámbito de sitio o de servicio. Tenga en cuenta que esta configuración solo afecta a las reuniones programadas; no afectan a las reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en Skype Empresarial.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reunión que se usan actualmente en la organización.  <br/> |
   
**Opciones de configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Devuelve información sobre la configuración de la conferencia para la organización. La configuración de conferencia determina aspectos como el tamaño máximo permitido para el contenido y los documentos de conferencia; el período de gracia del contenido (es decir, el tiempo durante el cual se almacenará el contenido antes de eliminarlo) y las direcciones URL para las descargas internas y externas del cliente admitido.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de configuración de conferencias.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Quita la colección especificada de opciones de configuración de conferencia.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una colección existente de opciones de configuración de conferencias.  <br/> |
   
**Opciones de configuración de acceso telefónico**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Devuelve información sobre los directorios de conferencia configurados en su organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información sobre cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local configurados para su uso en la organización.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) que se usa para las conferencias de acceso telefónico. DTMF permite a los usuarios que participan por teléfono en una conferencia controlar la configuración de la conferencia (por ejemplo, activar y desactivar el audio o bloquear y desbloquear la conferencia) con el teclado numérico del teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas regionales o minoritarios, admitidos para su uso con Skype Empresarial Server conferencias de acceso telefónico local. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype Empresarial Server. Esto ayuda a proporcionar interoperabilidad entre Skype Empresarial Server y Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre la conferencia.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Esta configuración determina cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nueva colección de opciones de señalización de multifrecuencia de tono dual (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre la conferencia.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Esta configuración determina cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de señalización de frecuencia múltiple de tono dual (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico. La conferencia de acceso telefónico local permite a los usuarios usar un teléfono "normal", móvil u otro dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica la configuración que determina cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de directiva de PIN**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información acerca de las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. La autenticación de PIN permite a los usuarios acceder a Skype Empresarial Server proporcionando un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal de cliente (PIN).  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o más directivas existentes de número de identificación personal de cliente (PIN).  <br/> |
   
**Otras configuraciones de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deshabilita una sala Skype Empresarial Server de reuniones. Una sala de reuniones es un dispositivo de conferencias diseñado para abordar escenarios de colaboración y videoconferencia en pequeñas salas de reuniones. Al deshabilitar un objeto de sala de reuniones, se quitan todos los Skype Empresarial Server específicos de Active Directory asignados a la cuenta de usuario que representa la sala de reuniones. Sin embargo, la cuenta de usuario de Active Directory en sí no se elimina.  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Habilita una Skype Empresarial Server de reuniones. Para habilitar una sala de reuniones, primero debe crear una cuenta de usuario de Active Directory que representa ese sistema. Tenga en cuenta que, aunque los objetos de la sala de reuniones se basan en las cuentas de usuario, estos objetos no se mostrarán cuando ejecute el cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Devuelve información sobre el aviso de declinación de responsabilidades de conferencias usado en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, aquéllos que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Devuelve información sobre todas las salas Skype Empresarial Server de reuniones configuradas para su uso en la organización.  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Mueve un objeto Skype Empresarial Server sala de reuniones de un grupo de registradores a otro.  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Borra el texto del encabezado y el cuerpo de la declinación de responsabilidades de conferencias utilizada en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, aquéllos que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica los valores de propiedad de una sala de reuniones Skype Empresarial Server existente.  <br/> |
   
**Configuración de pruebas**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de uso compartido de aplicaciones.  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Realiza una prueba para ver si un usuario puede conectar con el proveedor de servicios de audioconferencia. Estos proveedores son organizaciones de terceros que suministran servicios de audioconferencia a organizaciones. Entre otras cosas, los proveedores de audioconferencia permiten a los usuarios que no se encuentran en la oficina, y que no están conectados a la red corporativa o Internet, participar en la parte de audio de una conferencia o una reunión.  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Comprueba la capacidad de que un par de usuarios participen en una conferencia de audio o vídeo (A/V).  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Comprueba si un par de usuarios pueden participar en una conferencia web de Skype Empresarial Server que incluya actividades como compartir o ver PowerPoint diapositivas, pizarras o sondeos. El cmdlet también comprueba que el servicio de conferencia web de Skype Empresarial Server puede detectar Office Web Apps Server y que un cliente puede cargar un archivo PowerPoint para su difusión por Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Comprueba si un usuario puede participar en una sesión de conferencia de acceso telefónico local.  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Prueba un número de teléfono con un plan de marcado (antes denominado perfil de ubicación) y devuelve la regla de normalización que se aplicará al número, así como el número traducido después de haber aplicado la regla de normalización.  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Comprueba la capacidad de tres usuarios para participar en una conferencia Skype Empresarial Server Mobility Service. El servicio de movilidad permite a los usuarios de teléfonos móviles como iPhones y teléfonos Windows realizar actividades como intercambiar mensajes instantáneos e información de presencia; almacenar y recuperar el correo de voz internamente en lugar de con su proveedor inalámbrico, y aprovechar las funcionalidades de Skype Empresarial Server como llamadas a través del trabajo y conferencias de acceso telefónico local.  <br/> **Nota:** Los clientes que usan MCX no se admiten en Skype Empresarial Server 2019.|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para programar, unirse y, a continuación, realizar una conferencia en línea con la API web de comunicaciones unificadas (UCWA).  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Devuelve información de diagnóstico para las funciones de conferencia de datos incluidas en Skype Empresarial Server.  <br/> |
