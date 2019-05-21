---
title: Eventos de UCWA en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumen: Obtenga información sobre la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.'
ms.openlocfilehash: bbded70318190fb4fa68ab524a696183c97ff07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279700"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos de UCWA en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre la API Web de comunicaciones unificadas (UCWA) en Skype empresarial Server.
  
Skype empresarial Server usa la API Web de comunicaciones unificadas (UCWA) para una serie de propósitos, desde el acceso a Microsoft Exchange para las búsquedas de contactos hasta la actualización de presencia para clientes móviles.
  
UCWA escribirá los registros del comportamiento operativo como tipos de evento informativos, de advertencia y de error. En la siguiente tabla se describen los eventos que pueden escribir los componentes de UCWA.
  
|**Id. del evento**|**Tipo de evento**|**Resumen**|**Causa y solución**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |Se inicializó UCWA  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Error  <br/> |UCWA encontró una excepción inesperada durante la inicialización  <br/> |Se produjo un error inesperado durante la inicialización  <br/> Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la posible causa  <br/> |
|20003  <br/> |Error  <br/> |UCWA encontró una excepción no controlada  <br/> |Se produjo una excepción no controlada  <br/> Reinicie el servidor. Si persiste el problema, póngase en contacto con el soporte técnico  <br/> |
|20004  <br/> |Error  <br/> |No se puede obtener acceso a Exchange para fotos HD  <br/> |La conexión a Exchange no está disponible  <br/> Asegúrese de que la conexión a Exchange esté disponible  <br/> |
|20005  <br/> |Informativo  <br/> |Se recuperó el acceso a Exchange para fotos HD  <br/> |N/D  <br/> |
|20006  <br/> |Error  <br/> |No se puede obtener acceso a Exchange para la búsqueda de contactos  <br/> |La conexión a Exchange no está disponible  <br/> Asegúrese de que la conexión a Exchange esté disponible  <br/> |
|20007  <br/> |Informativo  <br/> |Se recuperó el acceso a Exchange para la búsqueda de contactos  <br/> |N/D  <br/> |
|20008  <br/> |Advertencia  <br/> |Se intentó un número de suscripciones de presencia mayor que el permitido por aplicación  <br/> |Se intentó un número de suscripciones de presencia mayor que el permitido por aplicación  <br/> Compruebe los clientes para determinar las suscripciones innecesarias  <br/> |
|20009  <br/> |Advertencia  <br/> |Se intentó un número de suscripciones de presencia mayor que el permitido por lote  <br/> |Se intentó un número de suscripciones de presencia mayor que el permitido por lote  <br/> Compruebe los clientes para determinar las suscripciones innecesarias  <br/> |
|20010  <br/> |Error  <br/> |No se pueden recuperar los datos en banda  <br/> |No se pueden recuperar los datos en banda  <br/> Si persiste el problema, póngase en contacto con el soporte técnico  <br/> |
|20011  <br/> |Error  <br/> |No se puede suscribir la presencia  <br/> |No se puede suscribir la presencia  <br/> Si persiste el problema, póngase en contacto con el soporte técnico  <br/> |
|20012  <br/> |Error  <br/> |Error al registrar el extremo  <br/> |Error al registrar el extremo  <br/> Si persiste el problema, póngase en contacto con el soporte técnico  <br/> |
|20013  <br/> |Error  <br/> |La MCU de mensajería instantánea no está disponible  <br/> |La MCU de mensajería instantánea no está disponible  <br/> Compruebe si la MCU de mensajería instantánea se está ejecutando  <br/> |
|20014  <br/> |Informativo  <br/> |Se recuperó la conexión a la MCU de mensajería instantánea  <br/> |N/D  <br/> |
|20015  <br/> |Error  <br/> |La MCU de audio y vídeo no está disponible  <br/> |La MCU de audio y vídeo no está disponible  <br/> Compruebe si la MCU de audio y vídeo se está ejecutando  <br/> |
|20016  <br/> |Informativo  <br/> |Se recuperó la conexión a la MCU de audio y vídeo  <br/> |N/D  <br/> |
|20017  <br/> |Error  <br/> |La MCU de AS no está disponible  <br/> |La MCU de AS no está disponible  <br/> Compruebe si la MCU de AS se está ejecutando  <br/> |
|20018  <br/> |Informativo  <br/> |Se recuperó la conexión a la MCU de AS  <br/> |N/D  <br/> |
|20019  <br/> |Error  <br/> |La MCU de datos no está disponible  <br/> |La MCU de datos no está disponible  <br/> Compruebe si la MCU de datos se está ejecutando  <br/> |
|20020  <br/> |Informativo  <br/> |Se recuperó la conexión a la MCU de datos  <br/> |N/D  <br/> |
|20021  <br/> |Error  <br/> |No se puede conectar la MCU de mensajería instantánea  <br/> |No se puede conectar la MCU de mensajería instantánea  <br/> Compruebe si la MCU de mensajería instantánea se está ejecutando  <br/> |
|20022  <br/> |Error  <br/> |No se puede conectar la MCU de audio y vídeo  <br/> |No se puede conectar la MCU de audio y vídeo  <br/> Compruebe si la MCU de audio y vídeo se está ejecutando  <br/> |
|20023  <br/> |Error  <br/> |No se puede conectar la MCU de AS  <br/> |No se puede conectar la MCU de AS  <br/> Compruebe si la MCU de AS se está ejecutando  <br/> |
|20024  <br/> |Error  <br/> |No se puede conectar la MCU de datos  <br/> |No se puede conectar la MCU de datos  <br/> Compruebe si la MCU de datos se está ejecutando  <br/> |
|20025  <br/> |Error  <br/> |No se puede obtener acceso a Active Directory para las fotos  <br/> |La conexión a Active Directory no está disponible  <br/> Asegúrese de que la conexión a Active Directory esté disponible  <br/> |
|20026  <br/> |Informativo  <br/> |Se recuperó el acceso a Active Directory para las fotos  <br/> |N/D  <br/> |
|20027  <br/> |Advertencia  <br/> |No se puede deserializar  <br/> |No se puede deserializar  <br/> Si persiste el problema, póngase en contacto con el soporte técnico  <br/> |
   

