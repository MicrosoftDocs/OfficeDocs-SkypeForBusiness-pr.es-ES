---
title: Administrar las directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumen: Obtenga información sobre cómo administrar las directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 96b2f5e27aa65931f5cd76499e1a3f66b817baa5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898147"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Administrar las directivas de conferencia en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo administrar las directivas de conferencia en Skype para Business Server.
  
En este tema se describe cómo administrar directivas de conferencia. Para obtener más información acerca de cómo planear e implementar una conferencia, vea [Plan para las conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencias en Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las directivas de conferencia le permiten definir una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, el ancho de banda y los aspectos jurídicos de las reuniones.
  
Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario. La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso. Si asigna una directiva a un usuario, esa configuración tendrá preferencia. Si no asigna una directiva de usuario, se aplicará la configuración de sitio. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.
  
Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global. Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Administrar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial

Para administrar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Administrar las directivas de conferencia mediante el uso de Skype para Shell de administración de servidor empresarial

Para administrar las reuniones mediante el uso de Skype para Shell de administración de servidor empresarial, use los cmdlets siguientes:
  
**Configuración de la directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
   

