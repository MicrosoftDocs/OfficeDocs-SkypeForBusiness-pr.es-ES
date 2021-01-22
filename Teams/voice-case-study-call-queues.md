---
title: Caso práctico Teams voice Contoso
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
description: Caso práctico de voz de Teams para empresas multinacionales
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918736"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Caso práctico Contoso: operadores automáticos y colas de llamadas

Contoso estaba familiarizado con los operadores automáticos y las colas de llamadas de su implementación local de Skype Empresarial. Para comprender cómo configurar los operadores automáticos en la nube y las colas de llamadas, revisaron el plan para los operadores automáticos de Teams y [las colas de llamadas.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Requisitos según el tipo de sitio

Según el tipo de sitio, Contoso tenía las siguientes necesidades:

- Tipo de sitio A: sistemas de telefonía tradicionales heredados 

  El tipo de sitio A es necesario para mantener el mismo número de teléfono asociado con el recepcionista que el número de sus operadores automáticos. Los departamentos clave de cada uno de estos sitios tendrían sus propias colas de llamadas que se enrutaría a los miembros del equipo. Había una combinación de sitios que usaban Sistema telefónico con enrutamiento directo y Sistema telefónico con planes de llamadas.  

- Tipo de sitio B: Skype Empresarial Telefonía IP empresarial 

  El tipo de sitio B tenía operadores automáticos y colas de llamadas existentes que era necesario migrar a Teams. Contoso necesitaba mantener los números de teléfono asociados con los operadores automáticos. Contoso movió la mayoría de estos sitios a Sistema telefónico con planes de llamadas. Sin embargo, en las pocas ubicaciones en las que planes de llamadas no estaba disponible, Contoso movió estos sitios a una configuración de enrutamiento directo.  

- Tipo de sitio C: Skype Empresarial Telefonía IP empresarial & de telefonía antigua tradicional 

  En el tipo de sitio C había operadores automáticos existentes que residían en el sistema de telefonía tradicional heredado. Las decisiones y configuraciones para este sitio eran las mismas que el tipo de sitio A.   

- Para todos los tipos de sitio, Contoso hizo las siguientes preguntas:

  - P: ¿Usaremos números nuevos o existentes? 
    A: Contoso ha decidido usar los números de teléfono existentes para asignar a la cuenta de servicio del operador automático. 

  - P: ¿Cuándo estará disponible el operador automático para aceptar llamadas entrantes? 
    A: Contoso decidió establecer el horario laboral y hacer que las llamadas recibidas después del horario laboral se redirijan a un operador automático "no laborable".  

  - P: ¿Cómo se enrutarán las llamadas a los miembros de una cola de llamadas: enrutamiento de attendant, serial o round robin? 
    A: Contoso ha decidido usar el enrutamiento de Attendant, 

  - P: ¿Cómo determinaremos cuándo debe o no recibir una llamada un usuario? 
    A: Contoso ha decidido usar las opciones de administración de llamadas para determinar si el agente está disponible: enrutamiento basado en presencia. 


## <a name="configuration"></a>Configuración

Los pasos para configurar un operador automático y una cola de llamadas incluyen los siguientes esquemas en Administrar [cuentas de recursos:](manage-resource-accounts.md) 

1. Obtenga un número de servicio. 

2. Obtenga una licencia gratuita de Sistema telefónico: licencia de usuario virtual o licencia de Sistema telefónico de pago para usarla con la cuenta de recursos o con una licencia de Sistema telefónico.

3. Cree la cuenta de recurso. Se requiere un operador automático o una cola de llamadas para tener una cuenta de recursos asociada. 

4. Asigne el sistema telefónico o un sistema telefónico: licencia de usuario virtual a la cuenta de recursos. Para obtener más información, [consulte Sistema telefónico de Microsoft 365: licencia de usuario virtual.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)

5. Asigne un número de teléfono de servicio a la cuenta de recursos a la que asignó licencias. 

6. Crear una cola de llamadas o un operador automático de Sistema telefónico 

7. Vincule la cuenta del recurso con una cola de llamadas o un operador automático. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sitios con sistema telefónico con enrutamiento directo 

Contoso tuvo que configurar el número de teléfono proporcionado por el operador local como el número de servicio en Office 365. 

- Para configurar un número de teléfono disponible mediante enrutamiento directo, Contoso siguió las instrucciones ubicadas en Administrar [cuentas de recursos.](manage-resource-accounts.md) Como Office 365 no es consciente de los números de teléfono locales, Contoso usó PowerShell para completar la configuración.   

- Para configurar el operador automático de la nube, Contoso ha seguido los pasos indicados en [Configurar un operador automático de la nube.](create-a-phone-system-auto-attendant.md) 

- Para configurar una cola de llamadas en la nube, Contoso ha seguido los pasos indicados en [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sitios con sistema telefónico con plan de llamadas

Contoso tuvo que portabilidad del número de teléfono usado para Skype Empresarial Telefonía IP empresarial operadores automáticos a Office 365 Phone System. Esto permitía asignar el mismo número como un número de servicio para usarlo como operador automático. 

- Para transferir el número de teléfono, Contoso siguió las instrucciones de Transferir números de teléfono a [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) y obtuvo instrucciones adicionales en Administrar números de teléfono [para su organización.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

- Para configurar un operador automático de la nube, Contoso ha seguido los pasos indicados en [Configurar un operador automático de la nube.](create-a-phone-system-auto-attendant.md)

-  Para configurar una cola de llamadas en la nube, Contoso ha seguido los pasos indicados en [Crear una cola de llamadas en la nube.](create-a-phone-system-call-queue.md)  

 