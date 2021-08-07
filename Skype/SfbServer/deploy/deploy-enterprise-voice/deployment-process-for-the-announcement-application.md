---
title: Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y pasos para la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 18345e8265ffed46f2e39d4acc8e0fca115731b4381efc64b98ecb4aba9e49c9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305932"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server
 
Proceso de implementación y pasos para la aplicación de anuncio en Skype Empresarial Server Telefonía IP empresarial.
  
La aplicación Anuncio es una característica Telefonía IP empresarial que le permite configurar lo que sucede con las llamadas a extensiones sin asignar (extensiones que son válidas para su organización, pero que no están asignadas a una persona o un teléfono). Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.
  
La aplicación Anuncio se instala como una característica de la aplicación grupo de respuesta en el servidor front-end o en el servidor Standard Edition al implementar Telefonía IP empresarial. Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.
  
En esta sección se proporciona información general sobre los pasos necesarios para implementar la aplicación Announcement. Debe implementar Telefonía IP empresarial antes de configurar los anuncios. Los componentes requeridos por la aplicación Anuncio se instalan y se habilitan al implementar Telefonía IP empresarial.
  
**Proceso de implementación de anuncios**

|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar opciones de anuncio  <br/> | Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS). <br/>  Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Crear o eliminar un anuncio en Skype Empresarial Server](create-an-announcement.md) <br/> [Crear o modificar un intervalo de números sin signo en Skype Empresarial Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Comprobar la implementación de anuncios  <br/> |Escuche los anuncios para comprobar que la configuración funciona correctamente.  <br/> |-  <br/> |[(Opcional) Comprobar la implementación del anuncio en Skype Empresarial](optional-verify-announcement-deployment.md) <br/> |
   

