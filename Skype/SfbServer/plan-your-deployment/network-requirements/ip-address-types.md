---
title: Configurar tipos de dirección IP en Skype Empresarial
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumen: Revise las consideraciones de tipo de dirección IP a continuación antes de implementar Skype para Business Server.'
ms.openlocfilehash: 82c2cac46efe2513c6506bf57ab5c181c7a32202
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892126"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurar tipos de dirección IP en Skype Empresarial

**Resumen:** Revise las consideraciones de tipo de dirección IP a continuación antes de implementar Skype para Business Server.

Implementar tipos de direcciones IP mediante el uso de la configuración de la topología que configurar en el generador de topología. En esta sección se describe cómo implementar tipos de direcciones IP en servidores Front-End, servidores de mediación y servidores perimetrales.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implementar tipos de direcciones IP en un servidor front-end

Con el generador, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor Front-End.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Para implementar los tipos de direcciones IP en un servidor front-end

1. En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** (también puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

2. En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para una configuración de pila dual, seleccione **Habilitar IPv4** e **IPv6 habilitar**.

   **Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**

   - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.

     > [!NOTE]
     > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

   - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la **dirección IP principal**.

   - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.

   - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.

> [!NOTE]
> No se admite la instalación de tarjetas de interfaz de red adicionales (NIC) para admitir la configuración de direcciones IP PSTN en servidores Front-End. Para obtener más información acerca de configuraciones compatibles de NIC de Skype para Business Server, vea [plataformas de hardware de servidor para Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implementar tipos de dirección IP en un servidor de mediación

Con el generador, realice los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implementar tipos de direcciones IP en un servidor de mediación

- En Topology Builder, en **grupos de servidores de mediación**, haga clic en el servidor dentro de un grupo de servidores y, a continuación, seleccione **Editar propiedades**. (Como alternativa, seleccione el servidor y, a continuación, haga clic en **Editar propiedades** en el menú **acción** ).

- En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.

   **Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**

  - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.

    > [!NOTE]
    > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

  - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la dirección IP principal.

  - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.

  - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.
> [!IMPORTANT]
> Sólo se admiten dos tarjetas de red en *dedicado* servidores de mediación. Si el rol de servidor de mediación está combinado en el Front-End, dos tarjetas de red no son compatibles. 

> [!NOTE]
> - Para obtener más información acerca de configuraciones compatibles de NIC de Skype para Business Server 2015, vea [Hardware de Skype para Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Para obtener más información acerca de configuraciones compatibles de NIC de Skype para Business Server 2019, vea [Hardware de Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Implementar tipos de dirección IP en un servidor perimetral

Con el generador, realice los pasos siguientes:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implementar tipos de direcciones IP en un servidor perimetral

1. En Topology Builder, en **grupos de servidores perimetrales**, haga clic en el servidor dentro de un grupo de servidores y, a continuación, seleccione **Editar propiedades**. (Como alternativa, seleccione el servidor y, a continuación, haga clic en **Editar propiedades** en el menú **acción** ).

2. En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir.

3. Es preciso proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.
