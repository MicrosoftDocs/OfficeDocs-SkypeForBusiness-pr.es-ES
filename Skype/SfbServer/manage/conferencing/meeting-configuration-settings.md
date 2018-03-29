---
title: Administrar opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Resumen: Conozca cómo administrar los valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Administrar opciones de configuración de reuniones en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar valores de configuración de Skype para Business Server 2015 de reunión.
  
This topic describes how to manage meeting configuration settings. Para obtener más información acerca de cómo planear e implementar la conferencia, consulte [Plan de conferencia en Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) y [conferencias de implementar en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las opciones de configuración de reunión definen el tipo de reuniones que pueden crear los usuarios, además de controlar cómo (o, incluso, si) los usuarios de conferencias anónimos o de acceso telefónico local pueden participar en las reuniones. Tenga en cuenta que esta configuración sólo afecta a las reuniones programadas; no afectan a reuniones ad hoc creadas haciendo clic en la opción Reunirse ahora en Skype para el negocio.
  
Las opciones de configuración de reuniones definen lo siguiente:
  
- Si los usuarios que realizan la llamada desde una red telefónica conmutada (RTC) pasan al salón de espera.
    
- Quién puede ser moderador.
    
- Si el tipo de conferencia está asignado de forma predeterminada.
    
- Si los usuarios anónimos (sin autenticar) se admiten de forma predeterminada.
    
Puede definir las características de reuniones utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor empresarial. 
  
Puede especificar configuración en el nivel global (que se crea de manera predeterminada) de la reunión, a nivel de sitio o grupo de nivel. De forma predeterminada, la configuración global define la experiencia de la reunión. Si crea una configuración a nivel de grupo, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración a nivel de grupo, se aplicará la configuración a nivel de sitio, si existe. Si no define la configuración a nivel de sitio, se aplicará la configuración global a todas las reuniones.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Administrar opciones de reunión mediante Skype para Panel de Control de servidor empresarial

Para administrar la configuración de reunión utilizando Skype para Panel de Control de servidor de negocios:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Administrar opciones de reunión mediante Skype para el Shell de administración de servidor empresarial

Para administrar las reuniones mediante Skype para el Shell de administración de servidor de negocio, use los siguientes cmdlets:
  
**Opciones de configuración de la reunión**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Devuelve información sobre las opciones de configuración de reunión en uso en la organización.  <br/> |
|[Nueva CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de reunión en el ámbito de sitio o de servicio.  <br/> |
|[Quitar CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Elimina una colección existente de opciones de configuración de reunión.  <br/> |
|[Conjunto de CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica las opciones de configuración de reuniones que se usan actualmente en la organización.  <br/> |
   

