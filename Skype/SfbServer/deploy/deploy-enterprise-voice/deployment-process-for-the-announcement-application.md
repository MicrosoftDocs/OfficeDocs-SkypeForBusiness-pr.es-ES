---
title: Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 08a52569dede43bbe54b1bf7e62f37114ba68853
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a>Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server 2015
 
Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Business Server Enterprise Voice.
  
La aplicación de anuncio es una característica de Enterprise Voice que le permite configurar lo que ocurre con las llamadas a extensiones sin asignar (extensiones que son válidas para su organización, pero no están asignadas a una persona o un teléfono). Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.
  
La aplicación de anuncio se instala como una característica de aplicación de grupo de respuesta en el servidor Front-End o Standard Edition al implementar Enterprise Voice. Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.
  
En esta sección se proporciona una visión general de los pasos necesarios para implementar la aplicación de anuncio. Debe implementar Enterprise Voice antes de configurar anuncios. Los componentes requeridos por la aplicación de anuncio están instalados y habilitados al implementar Enterprise Voice.
  
**Proceso de implementación del anuncio**

|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar opciones de anuncio  <br/> | Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS). <br/>  Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Crear o eliminar un anuncio en Skype para Business Server 2015](create-an-announcement.md) <br/> [Crear o modificar un intervalo de números sin asignar en Skype para Business Server 2015](create-or-modify-an-unassigned-number-range.md) <br/> |
|Comprobar la implementación de anuncios  <br/> |Escuche los anuncios para comprobar que la configuración funciona correctamente.  <br/> |-  <br/> |[(Opcional) Comprobación de la implementación de anuncio en Skype para profesionales de 2015](optional-verify-announcement-deployment.md) <br/> |
   

