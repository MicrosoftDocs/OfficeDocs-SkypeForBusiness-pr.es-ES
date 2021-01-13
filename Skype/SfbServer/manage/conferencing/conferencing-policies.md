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
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835280"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Administrar directivas de conferencia en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar directivas de conferencia en Skype Empresarial Server.
  
En este tema se describe cómo administrar directivas de conferencia. Para obtener más información acerca de cómo planear e implementar conferencias, vea [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las directivas de conferencia permiten definir una amplia variedad de opciones de programación y participación, desde si una reunión puede incluir audio y vídeo IP hasta el número máximo de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, el ancho de banda y los aspectos legales de las reuniones.
  
Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario. La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso. Si asigna una directiva a un usuario, dicha configuración tendrá prioridad. Si no asigna una directiva de usuario, se aplicará la configuración de sitio. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.
  
Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global. Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Administrar directivas de conferencia con el Panel de control de Skype Empresarial Server

Para administrar directivas de conferencia con el Panel de control de Skype Empresarial Server:
  
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Administrar directivas de conferencia mediante el Shell de administración de Skype Empresarial Server

Para administrar reuniones mediante el Shell de administración de Skype Empresarial Server, use los cmdlets siguientes:
  
**Configuración de directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
   

