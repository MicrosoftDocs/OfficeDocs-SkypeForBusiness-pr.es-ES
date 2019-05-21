---
title: Configurar tipos de dirección IP en Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Resumen: Revise las consideraciones de tipo de dirección IP a continuación antes de implementar Skype empresarial Server.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297053"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurar tipos de dirección IP en Skype Empresarial

**Resumen:** Revise las consideraciones de tipo de dirección IP a continuación antes de implementar Skype empresarial Server.

Para implementar los tipos de dirección IP, use la configuración de topología que configure en el generador de topología. En esta sección se describe cómo implementar los tipos de direcciones IP en servidores front-end, servidores de mediación y servidores perimetrales.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Implementar tipos de direcciones IP en un servidor front-end

Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor front-end.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Para implementar los tipos de direcciones IP en un servidor front-end

1. En **Grupo de servidores front-end Enterprise Edition**, haga clic con el botón secundario dentro de un grupo y seleccione **Editar propiedades** (también puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).

2. En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para obtener una configuración de pila doble, seleccione **Habilitar IPv4** y **Habilitar IPv6**.

   **Cuadro de diálogo Editar propiedades para el grupo de servidores front-end**

   - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.

     > [!NOTE]
     > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

   - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la **dirección IP principal**.

   - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.

   - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.

> [!NOTE]
> La instalación de tarjetas de interfaz de red (NICs) adicionales para admitir la configuración de la dirección IP de RTC (o por cualquier otro motivo) en los servidores front-end no es compatible. Para obtener más información sobre las configuraciones de NIC compatibles con Skype empresarial Server, consulte [plataformas de hardware de servidor para Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Implementar tipos de dirección IP en un servidor de mediación

Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor de mediación.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Para implementar tipos de direcciones IP en un servidor de mediación

- En el generador de topologías, en **grupos**de mediación, haga clic con el botón secundario en el servidor de un grupo y seleccione **Editar propiedades**. (También puede seleccionar el servidor y, a continuación, hacer clic en **Editar propiedades** en el menú **acción** ).

- En el cuadro de diálogo **Editar propiedades**, seleccione el tipo de dirección IP que desea configurar. Para establecer una configuración de doble pila, seleccione **Habilitar IPv4** y **Habilitar IPv6**, como se muestra en la figura siguiente.

   **Cuadro de diálogo Editar propiedades para el grupo Servidor de mediación**

  - **Usar todas las direcciones IP configuradas**. Seleccione esta opción si desea que se usen todas las direcciones IP definidas en el equipo.

    > [!NOTE]
    > Esta es la opción recomendada para la configuración para IP versión 6 (IPv6).

  - **Limitar el uso del servicio a las direcciones IP seleccionadas**. Seleccione esta opción para determinar una dirección específica en el servidor nuevo. Si selecciona esta opción, necesita introducir un valor para la dirección IP principal.

  - **Dirección IP principal**. Introduzca una dirección IP que el servidor usará para todas las comunicaciones excepto para red telefónica conmutada (RTC). La dirección IP introducida necesita coincidir con el formato del tipo de dirección seleccionado.

  - **Dirección IP de RTC**. Defina una dirección IP para la RTC cuando asigne un servidor de mediación en el servidor front-end. Esta dirección necesita coincidir con el formato del tipo de dirección seleccionado.
> [!IMPORTANT]
> Solo admitimos dos tarjetas de red en servidores de mediación *dedicados* . Si el rol de SServer de mediación se encuentra en el front-end, no se admiten las tarjetas de red dobles. 

> [!NOTE]
> - Para obtener más información sobre las configuraciones de NIC compatibles con Skype empresarial Server 2015, consulte [hardware para Skype empresarial server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Para obtener más información sobre las configuraciones de NIC compatibles con Skype empresarial Server 2019, consulte [hardware para Skype empresarial server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Implementar tipos de dirección IP en un servidor perimetral

Siga estos pasos para usar el generador de topología:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Para implementar tipos de direcciones IP en un servidor perimetral

1. En el generador de topologías, en **grupos de límites**, haga clic con el botón secundario en el servidor dentro de un grupo y seleccione **Editar propiedades**. (También puede seleccionar el servidor y, a continuación, hacer clic en **Editar propiedades** en el menú **acción** ).

2. En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir.

3. Es preciso proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.
