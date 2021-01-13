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
description: Proceso de implementación y pasos para la aplicación Anuncio en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812310"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Proceso de implementación de la aplicación Anuncio en Skype Empresarial Server
 
Proceso de implementación y pasos para la aplicación Anuncio en Skype Empresarial Server Telefonía IP empresarial.
  
La aplicación Anuncio es una característica de Telefonía IP empresarial que permite configurar lo que sucede con las llamadas a extensiones sin asignar (extensiones que son válidas para su organización, pero que no están asignadas a una persona o un teléfono). Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.
  
La aplicación Anuncio se instala como una característica de la aplicación Grupo de respuesta en el servidor front-end o en el servidor Standard Edition al implementar Telefonía IP empresarial. Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.
  
En esta sección se proporciona información general sobre los pasos necesarios para implementar la aplicación Anuncio. Debe implementar los Telefonía IP empresarial antes de configurar los anuncios. Los componentes requeridos por la aplicación Anuncio se instalan y habilitan al implementar Telefonía IP empresarial.
  
**Proceso de implementación de anuncios**

|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar opciones de anuncio  <br/> | Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS). <br/>  Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Crear o eliminar un anuncio en Skype Empresarial Server](create-an-announcement.md) <br/> [Crear o modificar un intervalo de números sin signo en Skype Empresarial Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Comprobar la implementación de anuncios  <br/> |Escuche los anuncios para comprobar que la configuración funciona correctamente.  <br/> |-  <br/> |[(Opcional) Comprobar la implementación de anuncios en Skype Empresarial](optional-verify-announcement-deployment.md) <br/> |
   

