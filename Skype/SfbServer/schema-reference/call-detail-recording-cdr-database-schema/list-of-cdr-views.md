---
title: Lista de vistas de CDR
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
description: Las vistas proporcionan una manera sencilla de acceder a la información sobre los escenarios más comunes utilizados para devolver datos de la base de datos de CDR. Se recomienda usar vistas para crear informes personalizados en lugar de usar las tablas reales de la base de datos de CDR; esto se debe a que es más probable que las vistas de base de datos mantengan la compatibilidad con versiones anteriores con versiones futuras.
ms.openlocfilehash: 0a3b40c9b31bb521075e78a1a8d46479200249d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813160"
---
# <a name="list-of-cdr-views"></a>Lista de vistas de CDR
 
Las vistas proporcionan una manera sencilla de acceder a la información sobre los escenarios más comunes utilizados para devolver datos de la base de datos de CDR. Se recomienda usar vistas para crear informes personalizados en lugar de usar las tablas reales de la base de datos de CDR; esto se debe a que es más probable que las vistas de base de datos mantengan la compatibilidad con versiones anteriores con versiones futuras.
  
|**Nombre de vista**|**Descripción**|
|:-----|:-----|
|[Vista ClientVersions](clientversions-0.md) <br/> |Devuelve información sobre los dispositivos o el software del cliente utilizados en una sesión de comunicación.  <br/> |
|[Vista ConferenceMessageCount](conferencemessagecount-0.md) <br/> |Devuelve información sobre la cantidad de mensajes enviada por usuarios en una conferencia.  <br/> |
|[Vista Conferencias](conferences-0.md) <br/> |Devuelve información de conferencia, como por ejemplo la hora de inicio, la hora de finalización y el organizador de la conferencia.  <br/> |
|[Vista ConferenceSessionDetails](conferencesessiondetails.md) <br/> |Devuelve información detallada de sesión de todas las sesiones de conferencia, como por ejemplo la hora de inicio y de finalización, los identificadores de usuarios, los códigos de respuesta y los identificadores de diagnóstico.  <br/> |
|[Vista ConferenceUris](conferenceuris-0.md) <br/> |Devuelve información sobre URI de conferencias utilizados en una conferencia  <br/> |
|[Vista ErrorReport](errorreport-0.md) <br/> |Devuelve información sobre los errores que se produjeron durante una sesión.  <br/> |
|[Vista FileTransfers](filetransfers.md) <br/> |Devuelve información sobre las sesiones de transferencia de archivos, incluido el nombre del archivo y si la transferencia fue aceptada, rechazada o cancelada.  <br/> |
|[Vista FocusJoinsAndLeaves](focusjoinsandleaves-0.md) <br/> |Devuelve información sobre las actividades de conexión y desconexión de las conferencias.  <br/> |
|[Vista McuJoinsAndLeaves](mcujoinsandleaves-0.md) <br/> |Devuelve información combinada sobre las actividades de conexión y desconexión de las conferencias (cada conexión a la conferencia se encuentra junto con la desconexión de la conferencia correspondiente).  <br/> |
|[Vista Mcus](mcus-0.md) <br/> |Devuelve información sobre servidores de conferencias.  <br/> |
|[Vista multimedia](media-0.md) <br/> |Devuelve información acerca de los tipos de medios utilizados en las sesiones de comunicación punto a punto.  <br/> |
|[Vista ProgressReport](progressreport-0.md) <br/> |Devuelve información sobre sesiones completadas.  <br/> |
|[Vista de registro](registration-0.md) <br/> |Devuelve información sobre los registros con Skype Empresarial Server 2015.  <br/> |
|[Vista SessionDetails](sessiondetails-0.md) <br/> |Returns information sobre sesiones punto a punto, incluidas las llamadas telefónicas VoIP-VoIP, las sesiones de mensajería instantánea entre dos participantes u otras sesiones de comunicación punto a punto.  <br/> |
|[Vista de usuario](user.md) <br/> |Devuelve información sobre los usuarios que han participado en sesiones de comunicación.  <br/> |
|[Vista VoIPDetails](voipdetails.md) <br/> |Devuelve información para las sesiones punto a punto en las que haya participado al menos un usuario VoIP (Voz sobre IP).  <br/> |
   

