---
title: Crear o modificar una regla de conversión para presentación del identificador del destinatario de la llamada en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Resumen: Conozca cómo definir una regla de traducción con una herramienta de traducción regla de la generación en Skype para Business Server 2015.'
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a>Crear o modificar una regla de conversión para presentación del identificador del destinatario de la llamada en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo definir una regla de traducción con una herramienta de traducción regla de la generación en Skype para Business Server 2015.
  
Si desea definir una regla de conversión especificando un conjunto de valores en la herramienta de **compilación de una regla de traducción** y habilitar Skype para Panel de Control de servidor empresarial generar el correspondiente modelo coincidente y regla de conversión para, siga estos pasos. También tiene la opción de escribir una expresión regular manualmente para definir el patrón de correspondencia y la regla de conversión. Para obtener información detallada, vea [creación o modificación de una regla de traducción de forma manual](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Para definir una regla mediante el uso de la herramienta Crear una regla de conversión

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. Para empezar a definir una regla de traducción, siga los pasos en [configurar un tronco con medios de derivación en Skype para Business Server 2015](configure-trunk-with-media-bypass.md) paso 10 o [configurar un tronco sin medios de derivación en Skype para Business Server 2015](configure-trunk-without-media-bypass.md) al paso 9.
    
3. En **Nombre**, en las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número objeto de la conversión.
    
4. (Opcional) En **Descripción**, escriba una descripción de la regla de traducción para llamadas de larga distancia de ejemplo nos internacional.
    
5. En la sección **Crear una regla de conversión** del cuadro de diálogo, especifique valores en los campos siguientes:
    
   - **Dígitos iniciales**: (opcional) especifique los dígitos iniciales de los números para los que desea que coincida el patrón. Por ejemplo, escriba + en este campo para hacer coincidir los números E.164 format (que empiezan por +).
    
   - **Longitud**: especifique el número de dígitos en el patrón de coincidencia y seleccione si desea que el patrón coincida con números de exactamente esta longitud, al menos esta longitud o de cualquier longitud. Por ejemplo, escriba 11 y selectAt menos en la lista desplegable para que coincida con los números que están por lo menos de 11 dígitos de longitud.
    
   - **Dígitos que se van a quitar**: (opcional) especifique el número de dígitos iniciales que se van a quitar. Por ejemplo, escriba 1 para limpiar el + desde el principio del número.
    
   - **Dígitos que se van a agregar**: (opcional) especifique los dígitos que se van a agregar a los números convertidos. Por ejemplo, escriba 011 si desea 011 anteponer a los números traducidos cuando se aplica la regla.
    
    Los valores que especifique en estos campos se reflejarán en los campos **Patrón con el que hacer coincidir** y **Regla de conversión**. Por ejemplo, si especifica los valores de ejemplo precedentes, la expresión regular resultante en el campo **Patrón con el que hacer coincidir** es:
    
    ^\+(\d{9}\d+)$
    
    El campo **Regla de conversión** especifica un patrón para el formato de los números convertidos. Este patrón tiene dos partes:
    
   - Un valor (por ejemplo, $1) que representa el número de dígitos en el patrón de coincidencia
    
   - (Opcional) Un valor que puede agregar si lo especifica en el campo **Dígitos a agregar**.
    
    Usando el anterior ejemplo valores 011$ 1 aparece en el campo **regla de traducción** .
    
    Cuando la regla de conversión se aplique, +441235551010 se convertirá en 011441235551010.
    
6. Haga clic en **Aceptar** para guardar la regla de conversión.
    
7. Haga clic en **Aceptar** para guardar la configuración de tronco.
    
8. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
   > [!NOTE]
   > Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  
### <a name="to-define-a-translation-rule-manually"></a>Para definir una regla de conversión de forma manual

1. Abre Skype para Panel de Control de servidor empresarial
    
2. Para empezar a definir una regla de traducción, siga los pasos en [configurar un tronco con medios de derivación en Skype para Business Server 2015](configure-trunk-with-media-bypass.md) paso 10 o [configurar un tronco sin medios de derivación en Skype para Business Server 2015](configure-trunk-without-media-bypass.md) al paso 9.
    
3. En el campo **Nombre** de las páginas **Nueva regla de conversión** o **Editar regla de conversión**, escriba un nombre que describa el patrón de número de objeto de la conversión.
    
4. (Opcional) En **Descripción**, escriba una descripción de la regla de la traducción, por ejemplo nos internacional a larga distancia para marcar.
    
5. Haga clic en **Editar** en la parte inferior de la sección **Crear una regla de conversión**.
    
6. Especifique lo siguiente en **Escribir una expresión regular**:
    
   - En **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.
    
   - En **Regla de conversión**, especifique un patrón para el formato de los números convertidos.
    
    Por ejemplo, si escribe ^\+(\d{9}\d+)$ en **este patrón de coincidencia** and011$ 1 en la **regla de conversión**, la regla se traducirá +441235551010 a 011441235551010.
    
7. Haga clic en **Aceptar** para guardar la regla de conversión.
    
8. Haga clic en **Aceptar** para guardar la configuración de tronco.
    
9. En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**. 
    
    > [!NOTE]
    > Cada vez que cree o modifique una regla de conversión, debe ejecutar el comando **Confirmar todo** para publicar el cambio de configuración. Para obtener más información, consulte [publicación de cambios a la configuración de enrutamiento de voz de Skype para el año 2015 de negocios pendientes](voice-route-config-changes.md) en la documentación de las operaciones.
  
## <a name="see-also"></a>Vea también

#### 

[Configurar un tronco con omisión de medios en Skype para Business Server 2015](configure-trunk-with-media-bypass.md)
  
[Configurar un tronco sin medios de derivación en Skype para Business Server 2015](configure-trunk-without-media-bypass.md)
  
[Publicar los cambios pendientes a la configuración de enrutamiento de voz de Skype para negocios 2015](voice-route-config-changes.md)
#### 

[Implementar la omisión de medios en Skype para Business Server 2015](deploy-media-bypass.md)

