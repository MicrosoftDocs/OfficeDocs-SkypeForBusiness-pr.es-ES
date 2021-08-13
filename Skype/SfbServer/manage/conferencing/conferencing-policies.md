---
title: Administrar directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumen: obtenga información sobre cómo administrar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: e3d1e9c3ef3ef50cadd5f1cce03508896cbb3950a03a889092e9fbf7d2d5b93b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301406"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Administrar directivas de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar directivas de conferencia en Skype Empresarial Server.
  
En este tema se describe cómo administrar directivas de conferencia. Para obtener más información acerca de cómo planear e implementar conferencias, vea [Plan for conferencing in Skype Empresarial Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las directivas de conferencia le permiten definir una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir. Puede usar directivas de conferencia para administrar aspectos de seguridad, ancho de banda y legales de las reuniones.
  
Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario. La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso. Si asigna una directiva a un usuario, dicha configuración tendrá prioridad. Si no asigna una directiva de usuario, se aplicará la configuración de sitio. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.
  
Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global. Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Administrar directivas de conferencia mediante Skype Empresarial Server Panel de control

Para administrar directivas de conferencia mediante Skype Empresarial Server Panel de control:
  
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Administrar directivas de conferencia mediante Skype Empresarial Server Shell de administración

Para administrar reuniones mediante Skype Empresarial Server Shell de administración, use los cmdlets siguientes:
  
**Configuración de directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
