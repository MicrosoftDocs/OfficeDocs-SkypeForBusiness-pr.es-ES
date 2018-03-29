---
title: Cola de grupos de respuesta cree nuevos o edite los existentes
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Las colas de respuesta grupo contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: f5223aaca700c10a25631131db69a55de1362ddc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Cola de grupos de respuesta: Crear nueva o editar existente
 
Las colas de respuesta grupo contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Nombre** Cada una de ellas debe tener un nombre. Escriba un nombre descriptivo para la cola.
    
- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre la cola.
    
- **Grupos** Seleccione los grupos de agentes que desea asignar a la cola. Haga clic en **Seleccionar** para agregar grupos de agentes a la lista. Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.
    
    Las flechas arriba y abajo mover un grupo de agentes seleccionados hacia arriba y hacia abajo en la lista. El orden de los grupos de agentes afecta al orden en el que Skype para Business Server busca un agente disponible. Es decir, el primer grupo de la lista se busca primero un agente disponible, seguido por el segundo grupo y así sucesivamente.
    
- **Activar el tiempo de espera de cola** Active esta casilla de verificación para especificar un período máximo de tiempo para que un llamador esperar en espera antes de que un agente responde a la llamada. Si selecciona esta opción, tendrá que especificar también lo siguiente:
    
  - **Tiempo de espera (segundos)** Seleccione o escriba el número máximo de segundos que un llamador puede esperar antes de que un agente responde a la llamada.
    
  - **Llamar a la acción** Seleccione la acción que se produce cuando se agota el tiempo de espera de una llamada. Las opciones son:
    
  - **Desconectar**
    
  - **Reenviar a correo de voz** Si selecciona esta opción, en la **dirección SIP**, escriba una dirección de correo de voz en el formato sip:<username> @ <domainname> (por ejemplo, sip:bob@contoso.com).
    
  - **Reenviar a número de teléfono** Si selecciona esta opción, en la **dirección SIP** escriba el número de teléfono en el formato sip:<number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).
    
  - **Reenviar a la dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En la **dirección SIP**, escriba el identificador URI para el usuario en el formato sip:<username>@<domainname>.
    
  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola para recibir llamadas cuando el tiempo de espera de llamadas.
    
- **Habilitar el desbordamiento de la cola** Active esta casilla de verificación para especificar un número máximo de llamadas que puede contener la cola. Si selecciona esta opción, tendrá que especificar también lo siguiente:
    
  - **Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.
    
  - **Reenviar la llamada** Seleccione qué llamada es tomar medidas cuando se alcanza el umbral de desbordamiento de la cola.
    
  - **Llamar a la acción** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de la cola. Las opciones son:
    
  - **Desconectar**
    
  - **Reenviar a correo de voz** Si selecciona esta opción, en la **dirección SIP**, escriba una dirección de correo de voz en el formato sip:<username> @ <domainname> (por ejemplo, sip:bob@contoso.com).
    
  - **Reenviar a número de teléfono** Si selecciona esta opción, en la **dirección SIP** escriba el número de teléfono en el formato sip:<number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).
    
  - **Reenviar a la dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En la **dirección SIP**, escriba el identificador URI para el usuario en el formato sip:<username>@<domainname>.
    
  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola a la que va a recibir llamadas, cuando se alcanza el umbral de desbordamiento de la cola.
    
Para obtener más información acerca de capacidades y características de los grupos de respuesta, vea [Planear la aplicación de grupo de respuesta en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeamiento. Para obtener más información acerca de cómo trabajar con colas, consulte [Administrar colas de grupo de respuesta](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de las operaciones.
  

