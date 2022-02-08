---
title: Asistente para certificados
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: El Asistente para certificados se usa para solicitar, asignar, quitar o ver certificados. Debe haber iniciado sesión como miembro del grupo RTCUniversalServerAdmins. No hace falta pertenecer a ningún otro grupo para solicitar un certificado a una entidad de certificación pública. Para solicitar un certificado de la infraestructura de clave pública (PKI) de su organización, debe confirmar qué pertenencias de grupo adicionales (si las hay) que necesitará. Durante la tarea Solicitar, puede especificar credenciales alternativas que se usarán para solicitar el certificado a la CA emisora de la PKI.
ms.openlocfilehash: b79d04b3fa4d5579b586b4c37cd49d48740523c5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393032"
---
# <a name="certificate-wizard"></a>Asistente para certificados
 
El Asistente para certificados se usa para **solicitar**, **asignar**, **quitar** o **ver** certificados. Debe haber iniciado sesión como miembro del grupo RTCUniversalServerAdmins. No hace falta pertenecer a ningún otro grupo para solicitar un certificado a una entidad de certificación pública. Para solicitar un certificado de la infraestructura de clave pública (PKI) de su organización, debe confirmar qué pertenencias de grupo adicionales (si las hay) que necesitará. Durante la tarea Solicitar, puede especificar credenciales alternativas que se usarán para solicitar el certificado a la CA emisora de la PKI.
  
Para solicitar un nuevo certificado, haga clic en  **Solicitar**.
  
Para asignar un certificado que todavía no se haya asignado, haga clic en  **Asignar**.
  
Para quitar un certificado que ya se había asignado, haga clic en  **Quitar**.
  
> [!NOTE]
> El botón **Quitar** solo está disponible si ya se había asignado un certificado. Si el botón **Quitar** no está disponible (atenuado), significa que no hay ningún certificado asignado.
  
Para ver una certificado asignado, haga clic en  **Ver**.
  
> [!NOTE]
> El botón **Ver** solo estará disponible si ya se había asignado un certificado. Si el botón **Ver** está atenuado en gris, significa que no hay ningún certificado asignado.
  
Para actualizar la pantalla de asignación de certificados, haga clic en  **Actualizar**.
  
Para importar un certificado que no figure en el almacén de certificados, haga clic en  **Importar certificado**.
  
> [!NOTE]
> La opción **Importar certificado** suele usarse para procesar un certificado que se recibe a través de un proceso distinto al de una solicitud del Asistente para certificados. Por ejemplo, el administrador de la PKI crea un certificado y hace que esté disponible para el usuario. Use **Importar certificado** para importar el certificado en el almacén de certificados del equipo y que esté disponible para Skype Empresarial Server para asignar.
  
Para completar el proceso de pedir una solicitud de certificado a una entidad de certificación de la organización que precisa la aprobación de un administrador de la entidad de certificación, haga clic en **Procesar solicitud pendiente**. La solicitud de certificado aparecerá con el estado de pendiente y mostrará el número de identificación de la solicitud pendiente. Para seguir procesando un certificado que tenga el estado de pendiente, haga clic en **Actualizar** para habilitar el botón **Procesar solicitud pendiente**. El botón **Procesar solicitud pendiente** dejará de estar deshabilitado (atenuado). A continuación, puede intentar recuperar la solicitud pendiente; sin embargo, la solicitud continuará teniendo el estado de pendiente hasta que se emita el certificado o el administrador de la entidad de certificación lo deniegue. El botón no estará disponible si no quedan solicitudes pendientes válidas creadas por el Asistente para certificados.
  

