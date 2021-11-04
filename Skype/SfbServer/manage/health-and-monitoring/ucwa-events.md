---
title: Eventos UCWA en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Resumen: obtenga información sobre la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.'
ms.openlocfilehash: 32022d44635e9560e28723812c1247fda38cf00d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763628"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Eventos UCWA en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre la API web de comunicaciones unificadas (UCWA) en Skype Empresarial Server.
  
Skype Empresarial Server la API web de comunicaciones unificadas (UCWA) para varios fines, desde el acceso a Microsoft Exchange para búsquedas de contactos hasta la actualización de la presencia de clientes móviles.
  
UCWA escribirá registros del comportamiento operativo como tipos de eventos Informational, Warning y Error. En la tabla siguiente se describen los eventos que pueden escribir los componentes de UCWA.
  
|**Id. de evento**|**Tipo de evento**|**Resumen**|**Causa y resolución**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informativo  <br/> |UCWA inicializado  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Error  <br/> |UCWA encontró una excepción inesperada durante la inicialización  <br/> |Se ha producido un error inesperado durante la inicialización  <br/> Examine los detalles de excepción en la entrada de registro de eventos asociada para determinar la posible causa  <br/> |
|20003  <br/> |Error  <br/> |UCWA encontró una excepción no controlada  <br/> |Se produjo una excepción no controlada  <br/> Reinicie el servidor. Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20004  <br/> |Error  <br/> |No se puede Exchange para la foto HD  <br/> |La conexión Exchange no está disponible  <br/> Asegúrese de que la conexión a Exchange está disponible  <br/> |
|20005  <br/> |Informativo  <br/> |Recuperado de no tener acceso a Exchange para la foto HD  <br/> |N/D  <br/> |
|20006  <br/> |Error  <br/> |No se puede acceder Exchange búsqueda de contactos  <br/> |La conexión Exchange no está disponible  <br/> Asegúrese de que la conexión a Exchange está disponible  <br/> |
|20007  <br/> |Informativo  <br/> |Recuperado de no poder buscar contacto en Exchange  <br/> |N/D  <br/> |
|20008  <br/> |Advertencia  <br/> |Intentar suscribirse a más de las suscripciones de presencia permitidas por aplicación  <br/> |Intentar suscribirse a más de las suscripciones de presencia permitidas por aplicación  <br/> Comprobar si hay suscripciones innecesarias en los clientes  <br/> |
|20009  <br/> |Advertencia  <br/> |Intentar suscribirse a más de las suscripciones de presencia permitidas por lotes  <br/> |Intentar suscribirse a más de las suscripciones de presencia permitidas por lotes  <br/> Comprobar si hay suscripciones innecesarias en los clientes  <br/> |
|20010  <br/> |Error  <br/> |No se pueden recuperar los datos de la banda  <br/> |No se pueden recuperar los datos de la banda  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20011  <br/> |Error  <br/> |No se puede suscribir presencia  <br/> |No se puede suscribir presencia  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20012  <br/> |Error  <br/> |Error al registrar el extremo  <br/> |Error al registrar el extremo  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
|20013  <br/> |Error  <br/> |MCU de MENSAJERÍA INSTANTÁNEA no está disponible  <br/> |MCU de MENSAJERÍA INSTANTÁNEA no está disponible  <br/> Ver si mi MCU se está ejecutando  <br/> |
|20014  <br/> |Informativo  <br/> |Recuperado de un error al conectarse a mi MCU  <br/> |N/D  <br/> |
|20015  <br/> |Error  <br/> |Av MCU no está disponible  <br/> |Av MCU no está disponible  <br/> Ver si se está ejecutando AV MCU  <br/> |
|20016  <br/> |Informativo  <br/> |Recuperado de no conectarse a AV MCU  <br/> |N/D  <br/> |
|20017  <br/> |Error  <br/> |AS MCU no está disponible  <br/> |AS MCU no está disponible  <br/> Ver si se está ejecutando AS MCU  <br/> |
|20018  <br/> |Informativo  <br/> |Recuperado de no conectarse a AS MCU  <br/> |N/D  <br/> |
|20019  <br/> |Error  <br/> |MCU de datos no está disponible  <br/> |MCU de datos no está disponible  <br/> Ver si se está ejecutando MCU de datos  <br/> |
|20020  <br/> |Informativo  <br/> |Recuperado de un error al conectarse a MCU de datos  <br/> |N/D  <br/> |
|20021  <br/> |Error  <br/> |No se puede unirse a MCU de MENSAJERÍA INSTANTÁNEA  <br/> |No se puede unirse a MCU de MENSAJERÍA INSTANTÁNEA  <br/> Ver si mi MCU se está ejecutando  <br/> |
|20022  <br/> |Error  <br/> |No se puede unirse a AV MCU  <br/> |No se puede unirse a AV MCU  <br/> Ver si se está ejecutando AV MCU  <br/> |
|20023  <br/> |Error  <br/> |No se puede unirse a AS MCU  <br/> |No se puede unirse a AS MCU  <br/> Ver si se está ejecutando AS MCU  <br/> |
|20024  <br/> |Error  <br/> |No se puede unirse a MCU de datos  <br/> |No se puede unirse a MCU de datos  <br/> Ver si se está ejecutando MCU de datos  <br/> |
|20025  <br/> |Error  <br/> |No se puede tener acceso a Active Directory para la foto  <br/> |La conexión a Active Directory no está disponible  <br/> Asegúrese de que la conexión a Active Directory está disponible  <br/> |
|20026  <br/> |Informativo  <br/> |Recuperado de no tener acceso a Active Directory para la foto  <br/> |N/D  <br/> |
|20027  <br/> |Advertencia  <br/> |No se puede deserializar  <br/> |No se puede deserializar  <br/> Si el problema persiste, póngase en contacto con el soporte técnico del producto  <br/> |
   

