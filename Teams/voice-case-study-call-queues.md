---
title: Teams caso práctico de Contoso de voz
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams caso de voz para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121298"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Caso práctico de Contoso: Operadores automáticos y colas de llamadas

Contoso estaba familiarizado con los operadores automáticos y las colas de llamadas desde su implementación Skype Empresarial local. Para comprender cómo configurar operadores automáticos en la nube y colas de llamadas, revisaron Planear para Teams operadores automáticos y colas [de llamadas.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Requisitos según el tipo de sitio

Según el tipo de sitio, Contoso tenía las siguientes necesidades:

- Tipo de sitio A: Sistemas de telefonía heredados tradicionales 

  Tipo de sitio A necesario para mantener el mismo número de teléfono asociado al recepcionista que el número de sus operadores automáticos. Los departamentos clave de cada uno de estos sitios tendrían sus propias colas de llamadas que se enrutaría a los miembros del equipo. Había una mezcla de sitios que usaban Sistema telefónico con enrutamiento directo y Sistema telefónico con planes de llamadas.  

- Tipo de sitio B: Skype Empresarial Telefonía IP empresarial 

  El tipo de sitio B tenía operadores automáticos y colas de llamadas existentes que necesitaban migrar a Teams. Contoso necesitaba mantener los números de teléfono asociados con los operadores automáticos. Contoso movió la mayoría de estos sitios a Sistema telefónico con planes de llamadas. Sin embargo, en las pocas ubicaciones en las que los planes de llamadas no estaba disponible, Contoso movió estos sitios a una configuración de enrutamiento directo.  

- Tipo de sitio C: Skype Empresarial Telefonía IP empresarial & de telefonía tradicional heredada 

  El tipo de sitio C tenía operadores automáticos existentes que residían en el sistema de telefonía tradicional heredado. Las decisiones y configuraciones de este sitio eran las mismas que el tipo de sitio A.   

- Para todos los tipos de sitio, Contoso hizo las siguientes preguntas:

  - P: ¿Usaremos números nuevos o existentes? 
    A: Contoso decidió usar números de teléfono existentes para asignarse a la cuenta de servicio para el operador automático. 

  - P: ¿Cuándo estará disponible el operador automático para aceptar llamadas entrantes? 
    A: Contoso decidió establecer el horario laboral y hacer que las llamadas recibidas después del horario laboral se redirijan a un operador automático "después del horario laboral".  

  - P: ¿Cómo se enrutarán las llamadas a los miembros de una cola de llamadas: enrutamiento de operador, serie o round robin? 
    A: Contoso decidió usar el enrutamiento de Attendant, 

  - P: ¿Cómo determinaremos cuándo un usuario debe o no recibir una llamada? 
    A: Contoso decidió usar las opciones de administración de llamadas para determinar si el agente está disponible: enrutamiento basado en presencia. 


## <a name="configuration"></a>Configuración

Los pasos para configurar un operador automático y una cola de llamadas incluyen los siguientes esquemas en [Administrar cuentas de recursos:](manage-resource-accounts.md) 

1. Obtener un número de servicio. 

2. Obtenga una licencia Sistema telefónico de usuario virtual o una licencia de Sistema telefónico pago para usar con la cuenta de recursos o una Sistema telefónico licencia.

3. Cree la cuenta de recursos. Se requiere un operador automático o una cola de llamadas para tener una cuenta de recursos asociada. 

4. Asigne la Sistema telefónico o una Sistema telefónico: licencia de usuario virtual a la cuenta de recursos. Para obtener más información, [vea Microsoft 365 Sistema telefónico: licencia de usuario virtual.](./teams-add-on-licensing/virtual-user.md)

5. Asigne un número de teléfono de servicio a la cuenta de recursos a la que asignó licencias. 

6. Crear una cola Sistema telefónico llamada o un operador automático 

7. Vincule la cuenta de recursos con una cola de llamadas o un operador automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sitios con Sistema telefónico con enrutamiento directo 

Contoso tenía que configurar el número de teléfono proporcionado por el operador local como el número de servicio en Office 365. 

- Para configurar un número de teléfono disponible a través de Enrutamiento directo, Contoso siguió las instrucciones que se encuentran en [Administrar cuentas de recursos.](manage-resource-accounts.md) Como Office 365 no conoce los números de teléfono locales, Contoso usó PowerShell para completar la configuración.   

- Para configurar el operador automático en la nube, Contoso siguió los pasos descritos en [Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md) 

- Para configurar una cola de llamadas en la nube, Contoso siguió los pasos descritos en [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sitios con Sistema telefónico con plan de llamadas

Contoso tenía que portabilidad el número de teléfono que se usaba para Skype Empresarial Telefonía IP empresarial operadores automáticos para Sistema telefónico de Office 365. Esto permitía asignar el mismo número que un número de servicio para usarlo como operador automático. 

- Para portabilidad del número de teléfono, Contoso siguió las instrucciones de Transferir números de teléfono a [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) y obtuvo instrucciones adicionales en Administrar números de teléfono [para su organización.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Para configurar un operador automático en la nube, Contoso siguió los pasos descritos en [Configurar un operador automático en la nube.](create-a-phone-system-auto-attendant.md)

-  Para configurar una cola de llamadas en la nube, Contoso siguió los pasos descritos en [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)  

