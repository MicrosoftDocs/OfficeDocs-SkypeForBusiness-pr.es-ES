---
title: Proceso de implementación de la aplicación de anuncio en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 5adaea25903968935cbaa00639546926781c004c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888074"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Proceso de implementación de la aplicación de anuncio en Skype para Business Server
 
Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Business Server Enterprise Voice.
  
La aplicación de anuncio es una característica de Enterprise Voice que le permite configurar lo que ocurre con las llamadas a extensiones sin asignar (extensiones que son válidas para su organización, pero no están asignadas a una persona o un teléfono). Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.
  
La aplicación de anuncio se instala como una característica de aplicación de grupo de respuesta en el servidor Front-End o Standard Edition al implementar Enterprise Voice. Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.
  
En esta sección se proporciona una visión general de los pasos necesarios para implementar la aplicación de anuncio. Debe implementar Enterprise Voice antes de configurar anuncios. Los componentes requeridos por la aplicación de anuncio están instalados y habilitados al implementar Enterprise Voice.
  
**Proceso de implementación de anuncios**

|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar opciones de anuncio  <br/> | Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS). <br/>  Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Crear o eliminar un anuncio en Skype para Business Server](create-an-announcement.md) <br/> [Crear o modificar un intervalo de números sin asignar en Skype para Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Comprobar la implementación de anuncios  <br/> |Escuche los anuncios para comprobar que la configuración funciona correctamente.  <br/> |-  <br/> |[(Opcional) Comprobación de la implementación de anuncio en Skype para la empresa](optional-verify-announcement-deployment.md) <br/> |
   

