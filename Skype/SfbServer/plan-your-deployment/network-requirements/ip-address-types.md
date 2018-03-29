---
title: Configurar tipos de dirección IP en Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumen: Revisar las consideraciones de tipo de dirección IP a continuación antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: facfff432cfcde74af737b5a7c5db87d36f3eb41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurar tipos de dirección IP en Skype Empresarial
 
**Resumen:** Revisar las consideraciones de tipo de dirección IP a continuación antes de implementar Skype para Business Server 2015.
  
Implementar tipos de direcciones IP mediante la configuración de la topología que se configura en el generador de topología. En esta sección se describe cómo implementar tipos de direcciones IP en los servidores frontales, los servidores de mediación y servidores perimetrales.
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implementar tipos de direcciones IP en un servidor front-end

Con el generador de topología, realice los pasos del procedimiento siguiente para implementar tipos de direcciones IP en un servidor Front-End.
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Para implementar los tipos de direcciones IP en un servidor front-end

1. En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** (también puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).
    
2. En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.
    
   **Editar el cuadro de diálogo Propiedades para el grupo de servidor Front-End**

  - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo. 
    
    > [!NOTE]
    > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6). 
  
  - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la **dirección IP principal**.
    
  - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.
    
  - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.
    
    > [!NOTE]
    > No se admite la instalación de tarjetas de interfaz de red adicionales (NIC) para admitir la configuración de direcciones IP PSTN en servidores frontales. Para obtener más información acerca de configuraciones compatibles de NIC para Skype para Business Server, vea [plataformas de hardware de servidor para Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implementar tipos de dirección IP en un servidor de mediación

Con el generador de topología, realice los pasos del procedimiento siguiente para implementar tipos de direcciones IP en un servidor de mediación.
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implementar tipos de direcciones IP en un servidor de mediación

- Generador de topología, en **grupos de mediación**, (ratón) en el servidor dentro de un grupo y, a continuación, seleccione **Editar propiedades**. (Como alternativa, seleccione el servidor y, a continuación, haga clic en **Editar propiedades** en el menú **acción** .)
    
- En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.
    
   **Editar el cuadro de diálogo Propiedades para el grupo de servidor de mediación**

  - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo. 
    
    > [!NOTE]
    > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6). 
  
  - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la dirección IP principal.
    
  - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.
    
  - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.
    
    > [!NOTE]
    > No se admite la instalación de NIC adicionales para admitir la configuración de direcciones IP PSTN en servidores independientes de mediación. Para obtener más información acerca de configuraciones compatibles de NIC para Skype para Business Server, vea [plataformas de hardware de servidor para Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). 
  
## <a name="deploy-ip-address-types-on-a-edge-server"></a>Implementar tipos de dirección IP en un servidor perimetral

Con el generador de topología, realice los pasos del procedimiento siguiente para implementar tipos de direcciones IP en un servidor perimetral.
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implementar tipos de direcciones IP en un servidor perimetral

1. Generador de topología, en **grupos de borde**, (ratón) en el servidor dentro de un grupo y, a continuación, seleccione **Editar propiedades**. (Como alternativa, seleccione el servidor y, a continuación, haga clic en **Editar propiedades** en el menú **acción** .)
    
2. En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir. En las siguientes figuras se muestra una configuración de pila dual para la interfaz interna y la interfaz externa.
    
   **Doble interfaz interna del servidor perimetral de apilada**

   **Apiladas servidor perimetral externo interfaz dual**

3. Es preciso proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.
    

