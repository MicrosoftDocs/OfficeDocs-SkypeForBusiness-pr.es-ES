---
title: Asistente para certificados
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: El Asistente para certificados se usa para solicitar, asignar, quitar o ver certificados. Debe haber iniciado sesión como miembro del grupo RTCUniversalServerAdmins. No hace falta pertenecer a ningún otro grupo para solicitar un certificado a una entidad de certificación pública. Para solicitar un certificado de infraestructura de clave pública (PKI) de su organización, es necesario que confirme lo que adicionales, si hay alguno, pertenencias a grupos que necesitará. Durante la tarea de la solicitud, puede escribir las credenciales que se utilizará para solicitar que el certificado desde su PKI entidad emisora de certificados.
ms.openlocfilehash: 6254ae2601387fa7ef6c6900fe7479db9d7c6ee3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001464"
---
# <a name="certificate-wizard"></a>Asistente para certificados
 
El Asistente para certificados se usa para **solicitar**, **asignar**, **quitar** o **ver** certificados. Debe haber iniciado sesión como miembro del grupo RTCUniversalServerAdmins. No hace falta pertenecer a ningún otro grupo para solicitar un certificado a una entidad de certificación pública. Para solicitar un certificado de infraestructura de clave pública (PKI) de su organización, es necesario que confirme lo que adicionales, si hay alguno, pertenencias a grupos que necesitará. Durante la tarea de la solicitud, puede escribir las credenciales que se utilizará para solicitar que el certificado desde su PKI entidad emisora de certificados.
  
Para solicitar un nuevo certificado, haga clic en **Solicitar**.
  
Para asignar un certificado que todavía no se haya asignado, haga clic en **Asignar**.
  
Para quitar un certificado que ya se había asignado, haga clic en **Quitar**.
  
> [!NOTE]
> El botón **Quitar** solo está disponible si ya se había asignado un certificado. Si el botón **Quitar** no está disponible (atenuado), significa que no hay ningún certificado asignado.
  
Para ver un certificado asignado, haga clic en **Ver**.
  
> [!NOTE]
> El botón **Ver** solo estará disponible si ya se había asignado un certificado. Si el botón **Ver** está atenuado en gris, significa que no hay ningún certificado asignado.
  
Para actualizar la pantalla de asignación de certificados, haga clic en **Actualizar**.
  
Para importar un certificado que no figure en el almacén de certificados, haga clic en **Importar certificado**.
  
> [!NOTE]
> La opción **Importar certificado** suele usarse para procesar un certificado que se recibe a través de un proceso distinto al de una solicitud del Asistente para certificados. Por ejemplo, el administrador de la PKI crea un certificado y hace que esté disponible para el usuario. **Importar certificado** de uso para importar el certificado en el certificado del equipo almacenar y ponerlo a disposición de Skype para Business Server asignar.
  
Para completar el proceso de pedir una solicitud de certificado a una entidad de certificación de la organización que precisa la aprobación de un administrador de la entidad de certificación, haga clic en **Procesar solicitud pendiente**. La solicitud de certificado aparecerá con el estado de pendiente y mostrará el número de identificación de la solicitud pendiente. Para seguir procesando un certificado que tenga el estado de pendiente, haga clic en **Actualizar** para habilitar el botón **Procesar solicitud pendiente**. El botón **Procesar solicitud pendiente** dejará de estar deshabilitado (atenuado). A continuación, puede intentar recuperar la solicitud pendiente; sin embargo, la solicitud continuará teniendo el estado de pendiente hasta que se emita el certificado o el administrador de la entidad de certificación lo deniegue. El botón no estará disponible si no quedan solicitudes pendientes válidas creadas por el Asistente para certificados.
  

