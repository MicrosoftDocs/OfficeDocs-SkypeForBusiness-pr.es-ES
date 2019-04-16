---
title: Implementar Calidad de servicio en clientes de Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Implementar la calidad de servicio (QoS) para los clientes de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869849"
---
# <a name="set-qos-on-windows-clients"></a>Configurar QoS en clientes de Windows

Puede usar QoS basada en Directiva dentro de la directiva de grupo para establecer el intervalo de puertos de origen para el valor de DSCP predefinido en el cliente de los equipos. Los intervalos de puertos especificados en la tabla siguiente son un punto de partida para crear una directiva para cada carga de trabajo.

_Se recomienda intervalos de puertos inicial_

Tipo de tráfico de medios| Intervalo de puertos de origen de cliente |Protocolo|Valor de DSCP|Clase de DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000 – 50,019|TCP/UDP|46|Desvío rápido (EF)|
|Vídeo| 50,020 – 50,039|TCP/UDP|34|Desvío garantizado (AF41)|
|Uso compartido de aplicaciones o pantalla| 50,040 – 50,059|TCP/UDP|18|Reenvío (AF21) asegurado|
| | | | |

Siempre que sea posible, configure las opciones de QoS basada en Directiva dentro de un objeto de directiva de grupo. Los siguientes pasos son muy similares a la [configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tiene algunos detalles adicionales que no sea necesarios.

Para crear una directiva de audio de QoS para equipos de 10 Windows unido a un dominio, primero inicie sesión en un equipo en el que se ha instalado Administración de directivas de grupo. Abra Administración de directivas de grupo (haga clic en Inicio, elija Herramientas administrativas y, a continuación, haga clic en administración de directivas de grupo) y, a continuación, complete los siguientes pasos:

1. En administración de directivas de grupo, busque el contenedor donde se debe crear la nueva directiva. Por ejemplo, si todos los equipos cliente se encuentran en una unidad organizativa denominada **clientes**, se debe crear la nueva directiva en la unidad organizativa de cliente.

2. Haga clic en el contenedor adecuado y, a continuación, haga clic en **crear un GPO en este dominio y vincularlo aquí**.

3. En el cuadro de diálogo **Nuevo GPO** , escriba un nombre para el nuevo objeto de directiva de grupo en el cuadro **nombre** y, a continuación, haga clic en **Aceptar**.

4. Haga clic en la directiva recién creada y, a continuación, haga clic en **Editar**.

5. En el Editor de administración de directiva de grupo, expanda **Configuración del equipo**, expanda **Configuración de Windows**, haga clic en **QoS basada en directiva**y, a continuación, haga clic en **Crear nueva directiva**.

6. En el cuadro de diálogo de **QoS basada en directiva** , en la página de apertura, escriba un nombre para la nueva directiva en el cuadro **nombre** . Seleccione **Especificar el valor de DSCP** y establezca el valor **46**. Deje **Especificar velocidad de aceleración saliente** no está seleccionada y, a continuación, haga clic en **siguiente**.

7. En la página siguiente, seleccione **sólo las aplicaciones con este nombre del archivo ejecutable** y escriba el nombre **Teams.exe**y, a continuación, haga clic en **siguiente**. Esta opción indica a la directiva de solo dar prioridad al tráfico coincidente desde el cliente de los equipos.

8. En la tercera página, asegúrese de que **cualquier dirección IP de origen** y **cualquier dirección IP de destino** están seleccionados y, a continuación, haga clic en **siguiente**. Estos dos valores Asegúrese de que se administrarán los paquetes independientemente de qué equipo (dirección IP) envía los paquetes y qué equipo (dirección IP) recibirán los paquetes.

9. En la cuarta página, seleccione **TCP y UDP** en la lista desplegable **Seleccione el protocolo que se aplica esta directiva de QoS** . TCP (Protocolo de Control de transmisión) y UDP (Protocolo de datagramas de usuario) son los dos protocolos de red usados con más frecuencia.

10. Bajo el encabezado, **Especifique el número de puerto de origen**, seleccione **desde este intervalo o el puerto de origen**. En el cuadro de texto que lo acompaña, escriba el intervalo de puertos reservado para las transmisiones de audioconferencias. Por ejemplo, si ha reservado puertos 50000 a través de puertos 50019 para el tráfico de audio, escriba el intervalo de puertos con este formato: **50000:50019**. Haga clic en **Finalizar**.

11. Repita los pasos del 5 al 10 para crear directivas para vídeo y uso compartido de aplicaciones y escritorio, sustituyendo los valores apropiados en los pasos 6 y 10.

Las nuevas directivas que se ha creado no surtirán efecto hasta que se ha actualizado la directiva de grupo en los equipos cliente. Aunque la directiva de grupo se actualiza periódicamente en su propio, puede forzar una actualización inmediata, siga estos pasos:

1. En cada equipo para el que desea actualizar la directiva de grupo, abra una consola de comandos. Asegúrese de que la consola de comandos está establecida en Ejecutar como administrador.

2. En el símbolo del sistema, escriba

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Compruebe los marcados de DSCP en el objeto de directiva de grupo

Para comprobar que se han establecido los valores desde el objeto de directiva de grupo, realice los pasos siguientes.

1. Abra una consola de comandos. Asegúrese de que la consola de comandos está establecida en Ejecutar como administrador.

2. En el símbolo del sistema, escriba:

   ``` powershell
   gpresult /R > gp.txt
   ```

   Esto generará un informe y enviarlo a un archivo de texto denominado gp.txt. Como alternativa, puede escribir el comando siguiente para generar los mismos datos en un informe HTML más legible llamado gp.html:

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Captura de pantalla de la ventana de la consola que se ejecuta el comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de pantalla de la ventana de la consola que se ejecuta el comando gpresult.")

3. En el archivo generado, busque el encabezado **Aplica objetos de directiva de grupo** y compruebe que los nombres de los objetos de directiva de grupo que creó anteriormente están en la lista de directivas aplicadas.

4. Abra el Editor del registro y vaya a:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Compruebe los valores de las entradas del registro que aparecen en la tabla 4.

   _Tabla 4. Valores de las entradas del registro de Windows para QoS_

   |          Nombre          |  Tipo  |    Datos     |
   |         :---:          |:---:   |    :---:    |
   |    Nombre de la aplicación    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP local        | REG_SZ |     \*      |
   | Longitud del prefijo de IP local | REG_SZ |     \*      |
   |       Puerto local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP remota        | REG_SZ |     \*      |
   |    Prefijo de dirección IP remota    | REG_SZ |     \*      |
   |      Puerto remoto       | REG_SZ |     \*      |
   |     Velocidad de limitación      | REG_SZ |     -1      |

5. Compruebe que es correcto para el cliente que está utilizando el valor de la entrada de nombre de la aplicación y compruebe que el valor de DSCP y el puerto Local entradas reflejan la configuración en el objeto de directiva de grupo.
