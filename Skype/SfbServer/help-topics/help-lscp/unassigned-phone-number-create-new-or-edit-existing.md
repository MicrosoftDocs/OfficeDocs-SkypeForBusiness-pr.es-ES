---
title: Número de teléfono sin asignar crear nuevo o editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: b4cdd3d4efad5299b855c546edf2359698ef6a47
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Número de teléfono sin asignar: Crear nuevo o editar existente
 
Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
  
> [!IMPORTANT]
> Cuando haya terminado de crear un intervalo de números sin asignar nuevo o editar uno existente, haga clic en **Aceptar** para volver a la página **Número sin asignar** que enumera todos los intervalos de números. Los cambios realizados en la página de **Nuevo sin asignar número de rango** o de la página **Editar Rage de número sin asignar** no comprometemos a la base de datos hasta que haga clic en **Confirmar todo** en la página **Número sin asignar** .
  
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.
  
- **Nombre** Escriba un nombre descriptivo que identifica el intervalo de números sin asignar. Tras guardar el rango, no se puede cambiar este nombre.
    
- **Número de intervalo** En el primer campo, escriba el número de comienzo del intervalo de números sin asignar. En el segundo campo, escriba el número final del rango.
    
  - El número inicial del intervalo debe ser menor o igual al número final.
    
  - Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.
    
  - El número debe coincidir con la expresión regular (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?. Esto significa que el número puede comenzar con la cadena de tel: (si no se especifica esa cadena se agregará automáticamente para usted), un signo más (+) y un dígito del 1 al 9. El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ";ext=número de extensión".
    
- **Servicio de anuncio** Seleccione el **anuncio** para la aplicación de anuncio controlar la llamada entrante o **Mensajería unificada de Exchange** para hacer una de Operador automático de Exchange UM controle la llamada entrante.
    
- Si seleccionó un **anuncio** para el **servicio de anuncios**:
    
  - **FQDN del servidor de destino** Seleccione el ID de servicio del servicio de aplicación que se ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este rango de números sin asignar.
    
  - **Anuncio** Seleccione el anuncio para este rango de números sin asignar.
    
-  Si ha seleccionado **Mensajería unificada de Exchange** para el **servicio de anuncios**:
    
  - **Número de teléfono del Operador automático** Seleccione el número de teléfono para el de Operador automático de Exchange UM.
    
Para obtener más información acerca de capacidades y características de anuncio, vea [Planear la aplicación de anuncio en Skype para negocios 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planificación. Para obtener más información sobre cómo trabajar con intervalos numéricos sin asignar, vea [Configurar el enrutamiento de sin asignar números de teléfono](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de las operaciones.
  

