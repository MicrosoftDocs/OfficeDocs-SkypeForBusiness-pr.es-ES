---
title: Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: 2188faaf80b3caa89acafd7fdf441ab895d11c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a>Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server 2015
 
Proceso de implementación y los pasos para la aplicación de anuncio en Skype para Telefonía IP empresarial de Business Server.
  
La aplicación de anuncio es una característica de Telefonía IP empresarial que le permite configurar lo que ocurre con las llamadas a extensiones sin asignar (extensiones que son válidos para su organización, pero no están asignadas a una persona o un teléfono). Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.
  
La aplicación de anuncio se instala como una función de aplicación de grupo de respuesta en el servidor Standard Edition o de servidor Front-End al implementar la Telefonía IP empresarial. Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.
  
Esta sección proporciona una visión general de los pasos necesarios para implementar la aplicación de anuncio. Debe implementar la Telefonía IP empresarial antes de configurar los anuncios. Los componentes necesarios para la aplicación de anuncio están instalados y habilitados al implementar la Telefonía IP empresarial.
  
**Proceso de implementación del anuncio**

|**Fase**|**Pasos**|**Funciones**|**Documentación sobre la implementación**|
|:-----|:-----|:-----|:-----|
|Configurar opciones de anuncio  <br/> | Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS). <br/>  Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Crear o eliminar un anuncio de Skype para Business Server 2015](create-an-announcement.md) <br/> [Crear o modificar un intervalo de números sin asignar en Skype para Business Server 2015](create-or-modify-an-unassigned-number-range.md) <br/> |
|Comprobar la implementación de anuncios  <br/> |Escuche los anuncios para comprobar que la configuración funciona correctamente.  <br/> |-  <br/> |[(Opcional) Comprobar la implementación del anuncio en Skype para negocios 2015](optional-verify-announcement-deployment.md) <br/> |
   

