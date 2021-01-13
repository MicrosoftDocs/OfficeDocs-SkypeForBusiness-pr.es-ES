---
title: Eventos de UCWA en Skype Empresarial Server
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
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumen: obtenga información sobre la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816670"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos de UCWA en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.
  
Skype Empresarial Server usa la API web de comunicaciones unificadas (UCWA) para diversos fines, desde el acceso a Microsoft Exchange para búsquedas de contactos hasta la actualización de la presencia de clientes móviles.
  
UCWA escribirá registros del comportamiento operativo como tipos de evento Informativo, Advertencia y Error. En la tabla siguiente se describen los eventos que pueden escribir los componentes de UCWA.
  
|**Id. de evento**|**Tipo de evento**|**Resumen**|**Causa y resolución**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inicializado  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Error  <br/> |UCWA encontró una excepción inesperada durante la inicialización  <br/> |Se ha producido un error inesperado durante la inicialización  <br/> Examine los detalles de la excepción en la entrada del registro de eventos asociada para determinar la posible causa  <br/> |
|20003  <br/> |Error  <br/> |UCWA encontró una excepción no controlada  <br/> |Se produjo una excepción no controlada  <br/> Reinicie el servidor. Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20004  <br/> |Error  <br/> |No se puede acceder a Exchange para fotos HD  <br/> |La conexión a Exchange no está disponible  <br/> Asegúrese de que la conexión a Exchange está disponible  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperado de un error de acceso a Exchange para fotos HD  <br/> |N/D  <br/> |
|20006  <br/> |Error  <br/> |No se puede obtener acceso a Exchange para la búsqueda de contactos  <br/> |La conexión a Exchange no está disponible  <br/> Asegúrese de que la conexión a Exchange está disponible  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperado de un error al buscar contacto en Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Advertencia  <br/> |Intentar suscribirse a suscripciones de presencia superiores a las permitidas por aplicación  <br/> |Intentar suscribirse a suscripciones de presencia superiores a las permitidas por aplicación  <br/> Comprobar si hay suscripciones innecesarias en los clientes  <br/> |
|20009  <br/> |Advertencia  <br/> |Intentar suscribirse a suscripciones de presencia superiores a las permitidas por lotes  <br/> |Intentar suscribirse a suscripciones de presencia superiores a las permitidas por lotes  <br/> Comprobar si hay suscripciones innecesarias en los clientes  <br/> |
|20010  <br/> |Error  <br/> |No se pueden recuperar datos en banda  <br/> |No se pueden recuperar datos en banda  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20011  <br/> |Error  <br/> |No se puede suscribir la presencia  <br/> |No se puede suscribir la presencia  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20012  <br/> |Error  <br/> |Error al registrar el extremo  <br/> |Error al registrar el extremo  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20013  <br/> |Error  <br/> |La MCU de mensajería instantánea no está disponible  <br/> |La MCU de mensajería instantánea no está disponible  <br/> Ver si la MCU de mensajería instantánea se está ejecutando  <br/> |
|20014  <br/> |Informativo  <br/> |Se recuperó de un error al conectarse a la MCU de mensajería instantánea  <br/> |N/D  <br/> |
|20015  <br/> |Error  <br/> |MCU av no está disponible  <br/> |MCU av no está disponible  <br/> Ver si la MCU av se está ejecutando  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperado de un error al conectarse a la MCU av  <br/> |N/D  <br/> |
|20017  <br/> |Error  <br/> |La MCU de AS no está disponible  <br/> |La MCU de AS no está disponible  <br/> Ver si se está ejecutando la MCU de AS  <br/> |
|20018  <br/> |Informativo  <br/> |Se recuperó de un error al conectarse a la MCU de AS  <br/> |N/D  <br/> |
|20019  <br/> |Error  <br/> |La MCU de datos no está disponible  <br/> |La MCU de datos no está disponible  <br/> Ver si la MCU de datos se está ejecutando  <br/> |
|20020  <br/> |Informativo  <br/> |Recuperado de un error al conectarse a la MCU de datos  <br/> |N/D  <br/> |
|20021  <br/> |Error  <br/> |No se puede unirse a la MCU de mensajería instantánea  <br/> |No se puede unirse a la MCU de mensajería instantánea  <br/> Ver si la MCU de mensajería instantánea se está ejecutando  <br/> |
|20022  <br/> |Error  <br/> |No se puede unirse a la MCU av  <br/> |No se puede unirse a la MCU av  <br/> Ver si la MCU av se está ejecutando  <br/> |
|20023  <br/> |Error  <br/> |No se puede unirse a la MCU de AS  <br/> |No se puede unirse a la MCU de AS  <br/> Ver si se está ejecutando la MCU de AS  <br/> |
|20024  <br/> |Error  <br/> |No se puede unirse a la MCU de datos  <br/> |No se puede unirse a la MCU de datos  <br/> Ver si la MCU de datos se está ejecutando  <br/> |
|20025  <br/> |Error  <br/> |No se puede obtener acceso a Active Directory para la foto  <br/> |La conexión a Active Directory no está disponible  <br/> Asegúrese de que la conexión a Active Directory esté disponible  <br/> |
|20026  <br/> |Informativo  <br/> |Se recuperó el acceso a Active Directory para la foto  <br/> |N/D  <br/> |
|20027  <br/> |Advertencia  <br/> |No se puede deserializar  <br/> |No se puede deserializar  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
   

