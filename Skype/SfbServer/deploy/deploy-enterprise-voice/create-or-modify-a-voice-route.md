---
title: Crear o modificar una ruta de voz en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Resumen: obtenga información sobre cómo crear o modificar una ruta de voz en Skype Empresarial Server mediante el Panel de control de Skype Empresarial Server.'
ms.openlocfilehash: c6f1e50971551866cfa6cb12eb6a259ac2f932f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105846"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Crear o modificar una ruta de voz en Skype Empresarial
 
**Resumen:** Obtenga información sobre cómo crear o modificar una ruta de voz en Skype Empresarial Server mediante el Panel de control de Skype Empresarial Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Para crear una ruta de voz mediante el Panel de control de Skype Empresarial Server

1. Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro de la función administrativa **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
4. Haga clic en **Ruta**.
    
5. Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.
    
6. En **Nombre**, escriba un nombre descriptivo para la ruta de voz.
    
7. (Opcional) En **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
8. Para especificar los patrones que desea que se ajusten **a** esta ruta, puede usar la herramienta Crear un patrón para que coincida con para generar una expresión regular o escribir la expresión regular manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores de la forma siguiente: Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: Introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba uno o más valores para los patrones que coincidan que no  *desea*  que esta ruta se acote. Por ejemplo, para excluir números a partir de +425237 de la ruta, escriba  un valor de +425237 en el campo Excepciones y, a continuación, haga clic en **Aceptar**.
    
   - Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta. Para obtener más información sobre cómo escribir expresiones regulares, [vea ".NET Framework Regular Expressions"](/dotnet/standard/base-types/regular-expressions). 
    
9. Seleccione **Suprimir identificador de** autor de la llamada si no desea que el identificador del teléfono que realiza la llamada saliente aparezca en el destinatario de la llamada. Si selecciona esta opción, debe especificar un **identificador** de autor de la llamada alternativo que aparecerá en la pantalla del identificador de autor de la llamada del destinatario.
    
10. Para asociar uno o varios troncos con la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione un tronco de la lista.
    
11. Para asociar uno o varios usos de red telefónica conmutada (RTC) con la ruta de voz, haga clic en **Seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación Telefonía IP empresarial cliente.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, vea Ver registros de uso [de RTC en Skype Empresarial](view-pstn-usage-records.md). > Para crear o editar registros de uso de RTC, vea Crear o modificar una directiva de voz y configurar registros de uso de [RTC en Skype Empresarial](voice-policy-and-pstn-usage-records.md)
  
12. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    > [!NOTE]
    > A diferencia de una directiva de voz, donde el orden en que se enumeran los registros de uso de RTC es importante, el orden en que los registros de uso de RTC se enumeran en la ruta de voz es insignificante. Sin embargo, se recomienda organizar la lista por frecuencia de uso. Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype Empresarial Server recorre la lista desde arriba hacia abajo). 
  
13. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
14. Haga clic en **Aceptar** para guardar la ruta de voz.
    
    > [!IMPORTANT]
    > Siempre que cree una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la configuración de](voice-route-config-changes.md)enrutamiento de voz en Skype Empresarial. 
  
### <a name="to-modify-a-voice-route"></a>Para modificar una ruta de voz

1. Abra el Panel de control de Skype Empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.
    
3. En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
   - Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.
    
4. En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.
    
5. (Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.
    
6. Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.
    
   - Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores de la forma siguiente: Puede especificar dos tipos de patrón de coincidencia:
    
   - **Dígitos iniciales para números que quiera permitir**: Introduzca los valores de prefijo que debe incluir esta ruta (incluso el signo + inicial, si fuera necesario). Por ejemplo, escriba +425 y, a continuación, haga clic en **Agregar**. Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.
    
   - **Excepciones**: Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **Excepciones**. Escriba uno o más valores para los patrones que coincidan que no  *desea*  que esta ruta se acote. Por ejemplo, para excluir números a partir de +425237 de la ruta, escriba  un valor de +425237 en el campo Excepciones y, a continuación, haga clic en **Aceptar**.
    
   - Para definir el patrón de  coincidencia manualmente, haga clic en Editar en la herramienta Crear un patrón para que coincida y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón de coincidencia para los números de teléfono de destino a los que se aplica la ruta.  Para obtener más información sobre cómo escribir expresiones regulares, [vea ".NET Framework Regular Expressions"](/dotnet/standard/base-types/regular-expressions). 
    
7. Seleccione **Suprimir identificador de** autor de la llamada si no desea que el identificador del teléfono que realiza la llamada saliente aparezca en el destinatario de la llamada. Si selecciona esta opción, debe especificar un **identificador** de autor de la llamada alternativo que aparecerá en la pantalla del identificador de autor de la llamada del destinatario.
    
8. Para asociar uno o varios troncos de red telefónica conmutada (RTC) con la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione un tronco de la lista.
    
9. Para asociar uno o más usos de  RTC con la ruta de voz, haga clic en Seleccionar y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación Telefonía IP empresarial de red.
    
    > [!NOTE]
    > Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, vea Ver registros de uso [de RTC en Skype Empresarial](view-pstn-usage-records.md). > Para crear o editar registros de uso de RTC, vea Crear o modificar una directiva de voz y configurar registros de uso de [RTC en Skype Empresarial](voice-policy-and-pstn-usage-records.md). 
  
10. Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.
    
    > [!NOTE]
    > A diferencia de una directiva de voz en la que el orden en que se enumeran los registros de uso de RTC es importante, el orden de los registros de uso de RTC en una ruta de voz es insignificante. Sin embargo, se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype Empresarial Server recorre la lista desde arriba hacia abajo). 
  
11. (Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.
    
12. Haga clic en **Aceptar**.
    
13. En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Siempre que cree o modifique una ruta de voz, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, [vea Publicar cambios pendientes en la](voice-route-config-changes.md) configuración de enrutamiento de voz en Skype Empresarial en la documentación sobre operaciones.
  
## <a name="see-also"></a>Ver también

[Ver registros de uso de RTC en Skype Empresarial](view-pstn-usage-records.md)
  
[Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial](voice-policy-and-pstn-usage-records.md)
  
[Publicar cambios pendientes en la configuración de enrutamiento de voz en Skype Empresarial](voice-route-config-changes.md)