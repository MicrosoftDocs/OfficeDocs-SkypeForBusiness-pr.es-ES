---
title: Administrar directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Resumen: Conozca cómo administrar directivas de conferencia en Skype para Business Server 2015.'
ms.openlocfilehash: 48ae623a9571b848ccb70b377416343eccca0c1c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-policies-in-skype-for-business-server-2015"></a>Administrar directivas de conferencia en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar directivas de conferencia en Skype para Business Server 2015.
  
En este tema se describe cómo administrar directivas de conferencia. Para obtener más información acerca de cómo planear e implementar la conferencia, consulte [Plan de conferencia en Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) y [conferencias de implementar en Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Las directivas de conferencia le permiten definir una amplia variedad de opciones de programación y participación, que van desde si una reunión puede incluir audio y vídeo IP hasta la cantidad máxima de personas que pueden asistir. Puede usar directivas de conferencia para administrar la seguridad, el ancho de banda y los aspectos jurídicos de las reuniones.
  
Puede definir la directiva de conferencias en tres niveles: ámbito global, ámbito de sitio y ámbito de usuario. La configuración se aplica a un usuario específico del ámbito más limitado al ámbito más extenso. Si asigna una directiva a un usuario, esa configuración tendrá preferencia. Si no asigna una directiva de usuario, se aplicará la configuración de sitio. Si no se aplica ni la directiva de usuario ni la de sitio, la directiva global proporcionará la configuración predeterminada.
  
Existe una directiva global predeterminada, de modo que no puede crear una nueva directiva global. Tampoco puede eliminar la directiva global existente, pero puede cambiar la directiva global para personalizar la configuración predeterminada.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Administrar directivas de conferencias con Skype para Panel de Control de servidor empresarial

Para administrar directivas de conferencias con Skype para Panel de Control de servidor de negocios:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Administrar directivas de conferencias con Skype para el Shell de administración de servidor empresarial

Para administrar las reuniones mediante Skype para el Shell de administración de servidor de negocio, use los siguientes cmdlets:
  
**Configuración de la directiva de conferencia**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas de conferencia que se han configurado para su uso en la organización.  <br/> |
|[Concesión CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Asigna una directiva de conferencia en el ámbito por usuario.  <br/> |
|[Nueva CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Crea una directiva de conferencia para usar en la organización.  <br/> |
|[Quitar CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Quita la directiva de conferencia especificada.  <br/> |
|[Conjunto de CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica una directiva de conferencia existente.  <br/> |
   

