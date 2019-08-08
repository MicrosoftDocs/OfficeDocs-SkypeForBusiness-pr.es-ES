---
title: Proceso de implementación para la aplicación de anuncios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Proceso de implementación y pasos para la aplicación de anuncios en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 2edb9364408658e9a164210a9fcd5a0196b10da7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245314"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Proceso de implementación para la aplicación de anuncios en Skype empresarial Server
 
Proceso de implementación y pasos para la aplicación de anuncios en Skype empresarial Server Enterprise Voice.
  
La aplicación de anuncios es una característica de voz empresarial que le permite configurar lo que sucede con las llamadas a extensiones no asignadas (extensiones que son válidas para su organización, pero que no están asignadas a una persona o teléfono). Por ejemplo, puede configurar las llamadas a números sin asignar para que se reproduzca un mensaje, se transfieran a otro destino o ambas cosas.
  
La aplicación de anuncios se instala como una característica de la aplicación de grupo de respuesta en el servidor front-end o el servidor Standard Edition al implementar la telefonía IP empresarial. Tiene que configurar Anuncios mediante la carga de los archivos de audio o la configuración de texto a voz (TTS) y la tabla de números sin asignar.
  
Esta sección proporciona una descripción general de los pasos necesarios para implementar la aplicación de anuncios. Debe implementar la telefonía IP empresarial antes de configurar los anuncios. Los componentes requeridos por la aplicación de anuncios se instalan y se habilitan al implementar la telefonía IP empresarial.
  
**Proceso de implementación de anuncios**

|**Fase**|**Pasos**|**Roles**|**Documentación de implementación**|
|:-----|:-----|:-----|:-----|
|Configurar opciones de anuncio  <br/> | Cree el anuncio grabando y cargando archivos de audio, o bien usando texto a voz (TTS). <br/>  Configure los intervalos de números no asignados de la tabla de números no asignados y asócielos al anuncio correspondiente. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Crear o eliminar un anuncio en Skype empresarial Server](create-an-announcement.md) <br/> [Crear o modificar un intervalo de números sin asignar en Skype empresarial Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Comprobar la implementación de anuncios  <br/> |Escuche los anuncios para comprobar que la configuración funciona correctamente.  <br/> |-  <br/> |[Faculta Comprobar la implementación de la presentación en Skype empresarial](optional-verify-announcement-deployment.md) <br/> |
   

