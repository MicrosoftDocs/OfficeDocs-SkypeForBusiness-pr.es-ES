---
title: Ponerse en contacto con el servicio rtc
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.pstnservicedesk
- ms.teamsadmincenter.voice.contactPSTNsupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: Cuando recibe números de teléfono o números de puerto (transferencia) para su organización, es posible que tenga que obtener ayuda y soporte técnico en el servicio RTC.
ms.openlocfilehash: b3925fbd473094b06133fb7cfe31479396434b80
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510283"
---
# <a name="pstn-service-desk"></a>Servicio RTC 

Hay un nuevo proceso para interactuar con el servicio RTC. Ahora puede abrir entradas, ver entradas y realizar un seguimiento de la comunicación en un único lugar integrado con el Centro de Teams administración. En este artículo se describe todo lo que necesita saber para ponerse en contacto con el servicio de atención al cliente.

> [!NOTE]
> A partir del 22 de julio de 2021, el sistema de correo electrónico actual se ha retirado.

Para ponerse en contacto con el servicio de atención al cliente:

1. Inicie sesión en el Centro Teams de administración de admin.teams.microsoft.com.

2. En el panel izquierdo, seleccione **Teléfono números.**

3. En la parte superior de la página, seleccione **Obtener soporte técnico de número de teléfono.** Verá el Centro de Teléfono de número.  

> [!NOTE]
> Solo alguien del mismo inquilino podrá crear un caso. Es decir, alguien de @fabrikam.com no puede crear un caso en nombre de @contoso.com. 

Desde el Teléfono de servicios de número, puede crear nuevos casos, ver casos existentes, comunicarse con el servicio de atención al cliente y administrar su perfil de usuario. Estas tareas se describen con más detalle en las secciones siguientes.

- **Teléfono de servicio de números**   – Vaya a la página principal del Portal. 

- **[Crear un nuevo caso](#create-a-new-case)**   – Enviar una nueva solicitud o consulta general. 

- **[Ver mis casos existentes:](#view-and-manage-existing-cases)** realice un seguimiento y supervise sus casos existentes. 

- **[Ver casos de mi empresa](#view-and-manage-existing-cases)**   – Controle y supervise los casos existentes de su empresa. Si sus compañeros de su empresa han abierto algún caso, puede buscar estos en esta vista.  

- **[Enviar comentarios:](#view-and-manage-existing-cases)** comparta sus comentarios con nosotros. 

- **[Su nombre]**   – Actualizar la página de perfil. 


## <a name="create-a-new-case"></a>Crear un nuevo caso

Para crear un nuevo caso, siga estos pasos:

1. Seleccione **Crear un nuevo caso** desde uno de los siguientes lugares:  

   - Desde la **Teléfono centro** de servicios de número, en la parte superior de la página o en el mosaico inferior.

   - Desde la **página Ver mis casos**  existentes.

   - Desde la **página Ver casos de mi** empresa.

2. Proporcione los detalles del caso como se describe detalladamente en [la sección siguiente.](#provide-case-details)

3. Después de escribir todos los valores, seleccione **Enviar**. Verá una pantalla nueva en la que podrá ver el número de caso.  

### <a name="provide-case-details"></a>Proporcionar detalles del caso

Para comprender los detalles del caso, Microsoft necesita la siguiente información:

- [Categoría De mayúsculas y minúsculas](#case-category)
- [País o región](#country-or-region)
- [Tipo de caso](#case-type)
- [Título de mayúsculas y minúsculas](#case-title)
- [Contactos adicionales para notificaciones](#additional-contacts-for-notifications)
- [Descripción](#description)
- [Documentos de soporte técnico adicionales](#additional-supporting-documents)

#### <a name="case-category"></a>Categoría De mayúsculas y minúsculas

Un caso puede tener una de dos categorías: 

- **Enviar una nueva solicitud:** elija esta opción si desea enviar una nueva solicitud. Por ejemplo, quiere enviar una solicitud de portabilidad o quiere comprar números de teléfono de Microsoft.  

- **Consulta general:** elija esta opción si tiene preguntas que le ayudarán a determinar su solicitud. Por ejemplo, debe saber si puede portabilidad de sus números inalámbricos a Microsoft o si Microsoft admite números gratuitos de vanidad. 

#### <a name="country-or-region"></a>País o región

Seleccione el país o región al que va a enviar este caso. Si tiene solicitudes para varios países, debe abrir un caso por país o región.  

#### <a name="case-type"></a>Tipo de caso

El tipo de caso puede ser uno de los siguientes:

- **Nombre de llamada personalizado (solo ee. UU.):** establezca un nombre de llamada personalizado en los números de teléfono de Microsoft. Esto solo se aplica a los números de teléfono de Estados Unidos. 

  - **Nombre de llamada personalizado para establecer (solo 15 caracteres):** el nombre de llamada personalizado que desea establecer. Nombre tiene un límite máximo de 15 caracteres.  

  - **Lista de números de teléfono:** la lista de números de teléfono para los que desea establecer un valor de nombre de llamada personalizado. Upload un archivo csv con la lista de números de teléfono.  

- **Puerto entre inquilinos:** mueva los números de teléfono de un inquilino a otro. Por ejemplo, tiene dos inquilinos diferentes dentro de Microsoft y desea mover los números de teléfono de un inquilino al otro.  

  - **Nombre de dominio del inquilino de origen:** el espacio empresarial desde el que desea mover números de teléfono a otro inquilino.  

  - **Identificador único del inquilino de origen:** el id. de inquilino del espacio empresarial de origen. Este es un campo opcional.  

  - **Nombre de dominio del inquilino de destino:** el espacio empresarial al que desea mover los números de teléfono.  

  - **Identificador único de inquilino de destino:** el id. de inquilino del inquilino de destino. Este es un campo opcional.  

  - **Hora de fecha solicitada*** : la fecha y la hora en las que desea mover los números del espacio empresarial de origen al espacio empresarial de destino. Vea Fecha y hora.

  - **Lista de números de teléfono:** la lista de números de teléfono que desea mover del inquilino de origen al inquilino de destino. Upload un archivo csv con la lista de números de teléfono. 

- **Cambio de tipo de inventario:** cambie el tipo de número de teléfono. Por ejemplo, desea cambiar los números de suscriptor de Microsoft a números de servicio. Para obtener más información sobre los tipos de números de teléfono compatibles con Microsoft, vea [Tipos de números de teléfono.](../different-kinds-of-phone-numbers-used-for-calling-plans.md)

  - **Convertir a:** seleccione esta opción para convertir los números en números de usuario o en números de servicio. 

  - **Fecha y hora preferida***: la fecha y hora en las que desea que se cambie el tipo de inventario de los números. Vea Fecha y hora para obtener más información.

  - **Casilla:** entiendo que para poder actualizar el tipo de inventario, mis números de teléfono deben estar sin asignar: Microsoft no puede procesar solicitudes de cambio de tipo de número de teléfono a menos que no se asignen los números de teléfono de su inquilino. Si solicita este cambio para una fecha futura, deberá asegurarse de que los números no se hansignado antes de la fecha y hora solicitadas. 

  - **Lista de números de teléfono:** la lista de números de teléfono cuyo tipo desea cambiar. Upload un archivo csv con la lista de números de teléfono. 

- **Nueva adquisición de TN:** compra nuevos números de teléfono de Microsoft.  

  - **Tipo de número:** seleccione el tipo de los números. Vea [Tipos de números de teléfono](../different-kinds-of-phone-numbers-used-for-calling-plans.md).

  - **Intentó obtener números de** teléfono desde el Portal del Centro de administración de Teams: ¿Ha intentado comprar estos números de teléfono en el portal del Centro de administración de Microsoft Teams, donde puede autoservicio?  

  - **Cantidad de números de teléfono necesarios:** el recuento de números de teléfono que desea comprar.  

  - **Estado o provincia:** el estado o provincia de su país o región para el que desea números de teléfono.  

  - **Ciudad:** la ciudad dentro del estado o provincia para la que desea números de teléfono.  

  - **Office dirección:** esto es específico solo para determinados países. Esta es la dirección del sitio de su oficina.  

  - **Lista de directorios:** esto es específico solo para determinados países. ¿Desea publicar la información de su empresa con los números de teléfono?  

- **Puerto en:** portabilidad de números de teléfono existentes de su proveedor de servicios actual a Microsoft.  

  - **Asigne un nombre al pedido de** portabilidad: proporcione un nombre fácil de recordar para la solicitud de portabilidad. 

  -  **Fecha y hora de portabilidad** solicitada * : la fecha y la hora en las que desea que los números se porten en Microsoft. Tenga en cuenta que esta no es una fecha de portabilidad garantizada, ya que el propietario del número actual tiene que aprobar primero nuestra solicitud de puerto. Vea Fecha y hora. 

  - **Lista de números de portabilidad:** la lista de números de teléfono que le gustaría portabilidad a Microsoft. Upload un archivo csv con la lista de números de teléfono. 

  - **Carta de autorización (LOA):** adjunte una LOA firmada y rellenada aquí. Microsoft no puede procesar una solicitud de puerto sin una LOA.  

- **Actualización de direcciones:** actualice la dirección de llamadas de emergencia. Tenga en cuenta que este campo solo se aplica a países seleccionados. 

  - **Id. de ubicación:** el id. de ubicación de la dirección de emergencia. 

  - **Lista de números de teléfono:** la lista de números de teléfono para los que desea cambiar la dirección de emergencia (escriba la dirección que desee en el campo Descripción). Upload un archivo csv con la lista de números de teléfono. 

***Fecha y hora.** Si selecciona País = Francia, fecha = 14/8/2021 y hora = 10 a.m., la solicitud se ejecutará el 14/8/2021 a las 10 a.m. Hora francesa. 

#### <a name="case-title"></a>Título de mayúsculas y minúsculas

Escriba un título que resuma su pregunta.  

#### <a name="additional-contacts-for-notifications"></a>Contactos adicionales para notificaciones

Escriba la lista de personas que recibirán notificaciones de estado automatizadas de Microsoft. Por ejemplo, desea poner un orden de portabilidad y desea que otros dos compañeros, además de usted mismo, reciban notificaciones de estado automatizadas. Proporcione las direcciones de correo electrónico de sus compañeros en la **sección Correos electrónicos de** notificación. Esta información es opcional. 

#### <a name="description"></a>Descripción

Describe lo que intentas lograr y enumera tus preguntas para el servicio RTC de Microsoft.  

#### <a name="additional-supporting-documents"></a>Documentos de soporte técnico adicionales

Upload documentos adicionales para su caso.  

## <a name="view-and-manage-existing-cases"></a>Ver y administrar casos existentes

Puede ver los casos seleccionando **Ver mis casos existentes** y seleccionando el número de caso. Al seleccionar un número de caso, se redirigirá a los detalles del caso. (También puede ver casos de empresa seleccionando **Ver casos de empresa).**  También puede:

- **Filtre los casos** **seleccionando Abrir casos**, **Todos los casos** o **Casos cerrados.**

- **Comuníquese con el servicio rtc** con respecto a su caso abriendo un caso existente, desplazándose hacia abajo y **seleccionando Agregar comentario.** Aparecerá una ventana nueva. Escriba el mensaje en el cuadro de comentario. Adjunte los documentos auxiliares (si están disponibles) que puedan ayudarle con su solicitud y seleccione **Enviar**.  

  Las respuestas del servicio RTC se mostrarán en la misma escala de tiempo. Cuando haya una actualización en su caso, recibirá una notificación por correo electrónico automatizada de la actualización. 

- **Para cancelar un caso,** vaya a un caso existente, desplácese hacia abajo y seleccione **Cancelar caso.** Seleccione un motivo para la cancelación en la lista desplegable y, a continuación, **seleccione Cancelar**.  

- **Resolver un caso:** si cree que la solicitud se ha completado, puede resolver un caso navegando a un caso existente, desplazándose hacia abajo y seleccionando **Resolver caso.** Seleccione **Cerrar;** el caso se mostrará ahora como **Resuelto: problema resuelto.**  


## <a name="related-topics-and-additional-resources"></a>Temas relacionados y recursos adicionales

- Para obtener ayuda relacionada con la configuración y configuración de números, licencias, tarifas o facturación, vea Contacto de soporte técnico para productos empresariales [: Ayuda para administradores.](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)

- Para obtener información sobre los planes de llamadas que están disponibles en su país o región, vea Disponibilidad de países y regiones para planes de [audioconferencias y llamadas.](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

- Para obtener información que puede ayudarle a seleccionar los tipos adecuados de números de teléfono para su organización, vea [Diferentes tipos de números de teléfono.](../different-kinds-of-phone-numbers-used-for-calling-plans.md)

- Para obtener información sobre cómo administrar números de teléfono para su organización, vea [Administrar números de teléfono para su organización.](manage-phone-numbers-for-your-organization.md)

- Para obtener información sobre los términos y condiciones de las llamadas de emergencia, consulte Términos y condiciones [de las llamadas de emergencia.](../emergency-calling-terms-and-conditions.md)
