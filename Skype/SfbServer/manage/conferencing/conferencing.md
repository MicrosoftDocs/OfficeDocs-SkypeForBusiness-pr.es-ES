---
title: Administrar conferencias en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumen: Aprenda a administrar conferencias en Skype empresarial Server.'
ms.openlocfilehash: 321241be405789e5a8b0f9440fddd09f738911ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818631"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Administrar conferencias en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar conferencias en Skype empresarial Server.
  
En este tema se describe cómo administrar conferencias. Para obtener más información sobre cómo planear e implementar conferencias, consulte [planear la Conferencia en Skype empresarial Server](../../plan-your-deployment/conferencing/conferencing.md) e [implementar conferencias en Skype empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
En Skype empresarial Server, se administran los detalles de las conferencias especificando la configuración y la configuración de la Directiva de la siguiente manera. Tenga en cuenta que los términos Conferencia y reunión se usan a veces indistintamente. Pero, en general, puede pensar en una reunión como una instancia específica de la Conferencia.
  
- **La configuración de directivas de conferencia** contiene una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, ancho de banda y aspectos jurídicos de las reuniones.
    
    Tenga en cuenta que las directivas de conferencia se aplican al usuario o sitio y no se pueden aplicar a una reunión determinada. Por lo tanto, la invitación a la reunión para la Conferencia puede crearse algunas semanas por adelantado, pero la Directiva de conferencia restrictiva debe aplicarse a la cuenta de Skype empresarial del organizador de la reunión justo antes de que se inicie la Conferencia. 
    
    Si una cuenta dedicada se usa para el rol de organizador de la reunión, la directiva de conferencia puede permanecer asignada a esa cuenta. Si el organizador de la reunión usa una cuenta general de Skype empresarial, debe quitar la Directiva una vez que haya finalizado la Conferencia.
    
- **Las opciones de configuración de reunión** definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones. Tenga en cuenta que estas opciones solo afectan a las reuniones programadas. La configuración de reunión se aplica por grupo, sitio o de forma global.
    
- Las **Opciones de configuración de conferencias** determinan aspectos como el máximo permitido para el contenido y los documentos de la reunión; cantidad máxima de ancho de banda para el servicio de conferencias de uso compartido de aplicaciones; límites de almacenamiento y períodos de expiración; las direcciones URL de las descargas internas y externas del cliente compatible. punteros a direcciones URL internas y externas donde los usuarios pueden obtener ayuda y recursos de conferencias; y los puertos que se usan para compartir aplicaciones, audio de cliente, transferencias de archivos y tráfico de medios.
    
    Esta configuración le permite administrar los servidores reales. Esta configuración solo se puede establecer mediante el shell de administración de Skype empresarial Server. 
    
- **La configuración de acceso telefónico** le permite definir información acerca de cómo los usuarios pueden acceder por teléfono a una conferencia y si lo tienen permitido o no. Usted especifica alguna información de acceso telefónico, como el número de acceso, desde la pestaña Conferencias del Panel de control y alguna información de acceso telefónico, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC desde la pestaña Enrutamiento de voz del Panel de control.
    
- **La configuración de la directiva de PIN** le permite ponerle nombre al PIN y definir el PIN que usan los participantes para el acceso telefónico local.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Administrar conferencias con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server

Puede administrar la mayoría de las directivas de conferencia y de configuración con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server. Algunas opciones de configuración solo están disponibles con el shell de administración de Skype empresarial Server.
  
- Para administrar la configuración de la directiva de conferencia:
    
  - En el Panel de control, seleccione **Conferencias | Directiva de conferencias**.
    
  - En PowerShell, busque los cmdlets **-CsConferencingPolicy**.
    
- Para administrar la configuración de reuniones:
    
  - En el Panel de control, seleccione **Conferencias | Configuración de reuniones**.
    
  - En el shell de administración de Skype empresarial Server, busque los cmdlets **-CsMeetingConfiguration** .
    
- Para administrar la configuración de números de acceso telefónico local:
    
  - En el Panel de control, seleccione **Conferencias | Número de acceso telefónico**.
    
  - En el shell de administración de Skype empresarial Server, busque los cmdlets **-CsDialInConferencing** .
    
- Para administrar la información de acceso telefónico local, como el plan de marcado, la directiva de voz, la ruta y el uso de RTC: 
    
  - En el Panel de control, seleccione **Conferencias | Enrutamiento de voz**.
    
  - En el shell de administración de Skype empresarial Server, busque los cmdlets **-CsDialPlan** y **-CsVoice** .
    
- Para administrar la configuración de la directiva de PIN:
    
  - En el Panel de control, seleccione **Conferencias | Directiva de PIN**.
    
  - En el shell de administración de Skype empresarial Server, busque los cmdlets **-CsPinPolicy** .
    
- Para administrar la configuración de la Conferencia, debe usar el shell de administración de Skype empresarial Server. Busque los cmdlets **-CsConferencingConfiguration**.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlets del shell de administración de Skype empresarial Server

Puede usar los siguientes cmdlets del shell de administración de Skype empresarial para administrar las conferencias: 
  
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
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una recopilación de opciones de configuración de reunión en el ámbito del sitio o del servicio. Tenga en cuenta que esta configuración solo afecta a las reuniones programadas; no afectan a las reuniones ad-hoc creadas al hacer clic en la opción reunirse ahora en Skype empresarial.  <br/> |
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
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información sobre cómo responde Skype empresarial Server cuando los usuarios se unen o salen de una conferencia de acceso telefónico local.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local que estén configurados para el uso en la organización La conferencia de acceso telefónico permite a los usuarios utilizar un teléfono móvil "normal", o un dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia en línea.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) que se usa para las conferencias de acceso telefónico local. DTMF permite a los usuarios que participan por teléfono en una conferencia controlar la configuración de la conferencia (por ejemplo, activar y desactivar el audio o bloquear y desbloquear la conferencia) con el teclado numérico del teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas regionales e minoritarios, que se pueden usar con las conferencias de acceso telefónico local de Skype empresarial Server. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype empresarial Server. Esto ayuda a proporcionar una interoperabilidad entre Skype empresarial Server y Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre la conferencia.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Esta configuración determina cómo responde Skype empresarial Server cuando los usuarios se unen a una conferencia de acceso telefónico local o salen de ella. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Crea una nueva recopilación de configuraciones de señalización tono de marcado de frecuencia múltiple (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar información sobre las conferencias.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Esta configuración determina cómo responde Skype empresarial Server cuando los usuarios se unen a una conferencia de acceso telefónico local o salen de ella.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico local. La conferencia de acceso telefónico local permite a los usuarios usar un teléfono "normal", móvil u otro dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica la configuración que determina cómo responde Skype empresarial Server cuando los usuarios se unen o salen de una conferencia de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de la directiva de PIN**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. La autenticación con PIN permite a los usuarios acceder a Skype empresarial Server proporcionando un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal (PIN) de cliente.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o varias directivas de número de identificación personal (PIN) de cliente.  <br/> |
   
**Otra configuración de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Deshabilita una sala de reuniones de Skype empresarial Server. Una sala de reuniones es un dispositivo de conferencias diseñado para abordar escenarios de colaboración y videoconferencia en pequeñas salas de reuniones. Al deshabilitar un objeto de sala de reuniones, se eliminan todos los atributos de Active Directory específicos de Skype empresarial Server asignados a la cuenta de usuario que representa la sala de reuniones. Sin embargo, la cuenta de usuario de Active Directory no se elimina.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Habilita una sala de reuniones de Skype empresarial Server. Para habilitar una sala de reuniones, primero debe crear una cuenta de usuario de Active Directory que representará ese sistema. Tenga en cuenta que, aunque los objetos de la sala de reuniones se basan en las cuentas de usuario, estos objetos no se mostrarán al ejecutar el cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Devuelve información sobre el aviso de declinación de responsabilidades de conferencias usado en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, los usuarios que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Devuelve información sobre todas las salas de reuniones de Skype empresarial Server configuradas para su uso en la organización.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Mueve un objeto de la sala de reuniones de Skype empresarial Server de un grupo de registradores a otro.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Borra el texto del encabezado y el cuerpo de la declinación de responsabilidades de conferencias usada en la organización. El aviso de declinación de responsabilidades de conferencias es un mensaje que se muestra a los usuarios que se unen a la conferencia a través de un hipervínculo (por ejemplo, los usuarios que pegan un vínculo que lleva a la conferencia en un explorador como Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica los valores de propiedad de un salón de reunión existente de Skype empresarial Server.  <br/> |
   
**Configuración de pruebas**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de uso compartido de aplicaciones.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Realiza una prueba para ver si un usuario puede conectar con el proveedor de servicios de audioconferencia. Estos proveedores son organizaciones de terceros que suministran servicios de audioconferencia a organizaciones. Entre otras cosas, los proveedores de audioconferencia permiten a los usuarios que no se encuentran en la oficina, y que no están conectados a la red corporativa o Internet, participar en la parte de audio de una conferencia o una reunión.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios para participar en una conferencia de audio o vídeo (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Comprueba si un par de usuarios puede participar en una conferencia Web de Skype empresarial Server que incluye actividades como compartir o ver diapositivas de PowerPoint, pizarras o sondeos. El cmdlet también comprueba que el servicio de conferencias web de Skype empresarial Server puede detectar Office Web Apps Server y que un cliente puede cargar un archivo de PowerPoint para su difusión por parte de Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Comprueba si un usuario puede participar en una sesión de conferencia de acceso telefónico local.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Prueba un número de teléfono con un plan de marcado (antes denominado perfil de ubicación) y devuelve la regla de normalización que se aplicará al número, así como el número traducido después de haber aplicado la regla de normalización.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Prueba la capacidad de tres usuarios para participar en una conferencia del servicio de movilidad de Skype empresarial Server. El servicio de movilidad permite a los usuarios de teléfonos móviles, como iPhone y Windows Phone, realizar tareas como mensajes instantáneos e información de presencia de Exchange; almacenar y recuperar el correo de voz internamente en lugar de con su proveedor de telefonía móvil; y aproveche las capacidades de Skype empresarial Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.  <br/> **Nota:** Los clientes que usan MCX no son compatibles con Skype empresarial Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Comprueba la capacidad de un par de usuarios de programar y dirigir una conferencia en línea, y participar en ella, con la API web de comunicaciones unificadas (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Devuelve información de diagnóstico para las capacidades de conferencia de datos incluidas en Skype empresarial Server.  <br/> |
   

