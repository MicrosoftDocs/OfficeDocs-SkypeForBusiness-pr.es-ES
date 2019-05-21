---
title: Implementar servidores perimetrales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Resumen: Aprenda a implementar servidores perimetrales en su entorno de Skype empresarial Server.'
ms.openlocfilehash: b8b55d4aea048faeb4bb8bda3cc0bd17f89f9f66
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306919"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Implementar servidores perimetrales en Skype empresarial Server
 
**Resumen:** Aprenda a implementar servidores perimetrales en su entorno de Skype empresarial Server.
  
Las siguientes secciones contienen los pasos que se deben seguir después de que se haya revisado la documentación del plan de servidores perimetrales de Skype empresarial Server en la documentación [de Skype empresarial Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) . Los pasos de implementación son los siguientes:
  
- Interfaces de red
    
- Instalación
    
- Certificados
    
- Iniciar los servidores perimetrales
    
## <a name="network-interfaces"></a>Interfaces de red

Como se indica en la planeación, deberá configurar la interfaz de red con DNS en la red perimetral que hospeda los servidores perimetrales o sin DNS en la red perimetral.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuración de la interfaz con servidores DNS en la red perimetral

1. Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    > [!NOTE]
    > Las subredes internas y externas no deben ser enrutables entre sí. 
  
2. En la interfaz externa, configurará **una** de las siguientes opciones:
    
   a. Tres direcciones IP estáticas en la subred de la red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales.
    
   b. Una dirección IP estática en la subred de la red perimetral externa y apunte la puerta de enlace predeterminada a la interfaz interna del firewall externo. Configure el adaptador DNS para apuntar a un par de servidores DNS perimetrales. Esta configuración solo es válida si ha configurado previamente su topología para que tenga valores no estándar en las asignaciones de puertos, que se trata en el artículo [crear una topología perimetral para Skype empresarial Server](create-your-edge-topology.md) .
    
3. En la interfaz interna, configure una dirección IP estática en la subred de la red perimetral interna y no establezca una puerta de enlace predeterminada. Configure el adaptador DNS para apuntar al menos a un servidor DNS, preferiblemente a un par de servidores DNS perimetrales.
    
4. Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Skype empresarial Server y los servidores de mensajería unificada de Exchange (UM).
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuración de la interfaz sin servidores DNS en la red perimetral

1. Instale dos adaptadores de red para cada servidor perimetral, uno para la interfaz interna y otro para la interfaz externa.
    
    > [!NOTE]
    > Las subredes internas y externas no deben ser enrutables entre sí. 
  
2. En la interfaz externa, configurará **una** de las siguientes opciones:
    
   a. Tres direcciones IP estáticas en la subred de la red perimetral externa. También necesitará configurar la puerta de enlace predeterminada en la interfaz externa, por ejemplo, para definir el enrutador orientado a Internet o el firewall externo como puerta de enlace predeterminada. Configure el adaptador DNS para apuntar a un servidor DNS externo, a poder ser, a un par de servidores DNS externos.
    
   b. Una dirección IP estática en la subred de la red perimetral externa. También necesitará configurar la puerta de enlace predeterminada en la interfaz externa, por ejemplo, para definir el enrutador orientado a Internet o el firewall externo como puerta de enlace predeterminada. Configure el adaptador DNS para apuntar a un servidor DNS externo o, a poder ser, a un par de servidores DNS externos. Esta configuración solo es válida si ha configurado previamente su topología para que tenga valores no estándar en las asignaciones de puertos, que se trata en el artículo [crear una topología perimetral para Skype empresarial Server](create-your-edge-topology.md) .
    
3. En la interfaz interna, configure una dirección IP estática en la subred de la red perimetral interna y no establezca una puerta de enlace predeterminada. Deje también la configuración del adaptador DNS vacía.
    
4. Cree rutas estáticas persistentes en la interfaz interna para todas las redes internas donde residen los clientes, Skype empresarial Server y los servidores de mensajería unificada de Exchange (UM).
    
5. Edite el archivo HOST en cada servidor perimetral para que contenga un registro para el servidor del próximo salto o IP virtual (VIP). Este registro será el director, servidor Standard Edition o grupo de servidores front-end que haya configurado como la dirección de Next hop del servidor perimetral en el generador de topología. Si está usando el equilibrio de carga de DNS, incluya una línea para cada miembro del grupo de próximos saltos.
    
## <a name="installation"></a>Instalación

Para completar estos pasos correctamente, tendrá que seguir los pasos que se indican en el artículo [crear una topología perimetral para Skype empresarial Server](create-your-edge-topology.md) .
  
1. Inicie sesión en el servidor que ha configurado para el rol de servidor perimetral con una cuenta que se encuentre en el grupo de administradores locales.
    
2. Necesitará el archivo de configuración de topología que copió al final de la documentación de la topología del servidor perimetral en este equipo. Obtenga acceso a los medios externos en los que ha colocado ese archivo de configuración (como una unidad USB o compartir).
    
3. Inicie el **Asistente para la implementación**.
    
4. Una vez que se abra el asistente, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**.
    
5. El asistente ejecutará comprobaciones para ver si algo está instalado. Como esta es la primera vez que se ejecuta el asistente, deseará comenzar en el **paso 1. Instale el almacén de configuración local.**
    
6. Aparecerá el cuadro **de diálogo Configurar réplica local del almacén de administración central** . Debe hacer clic en **Importar desde un archivo (recomendado para servidores perimetrales)**.
    
7. Desde aquí, vaya a la ubicación de la topología que exportó anteriormente, seleccione el archivo .zip, haga clic en **Abrir** y después haga clic en **Siguiente**.
    
8. El Asistente para la implementación leerá el archivo de configuración y escribirá el archivo de configuración XML en el equipo local.
    
9. Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.
    
10. En el Asistente para la implementación, haga clic en **paso 2. Configurar o quitar componentes de Skype empresarial Server**. El asistente instalará los componentes de Edge de Skype empresarial Server especificados en el archivo de configuración XML que se ha almacenado en el equipo local.
    
11. Una vez completada la instalación, puede seguir los pasos de la sección **certificados** que se muestra a continuación.
    
## <a name="certificates"></a>Certificados

Los requisitos de certificados para el servidor perimetral se pueden encontrar en la documentación de planeación de certificados perimetrales. Los pasos para configurar los certificados se muestran a continuación.
  
> [!NOTE]
> Al ejecutar el Asistente para certificados, debe haber iniciado sesión como una cuenta que tenga los permisos correctos para el tipo de plantilla de certificado que va a usar. De forma predeterminada, una solicitud de certificado de Skype empresarial Server va a usar la plantilla de certificado de servidor Web. Si ha iniciado sesión con una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado a través de esta plantilla, vuelva a comprobar para asegurarse de que se ha asignado al grupo los permisos de inscripción para usar esa plantilla. 
  
### <a name="internal-edge-interface-certificates"></a>Certificados de interfaz de servidor perimetral interno

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. descargar o exportar la cadena de certificación de la entidad emisora

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;ninguna. Descargar con el sitio web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;operaciones. Inicie sesión en un servidor de Skype empresarial en su red interna como miembro del grupo de administradores local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Abra **Inicio**, **ejecute** (o **Busque** y **ejecute** ) y, a continuación, escriba lo siguiente:
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Por ejemplo:
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. En la página web certsrv de la entidad emisora de certificados, en **seleccionar una tarea**, haga clic en **descargar un certificado de CA, una cadena de certificados o una CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cuarta. En **Descargar certificado de CA, cadena de certificados o CRL**, haga clic en **Descargar cadena de certificados de CA**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. En el cuadro **Descarga de archivos**, haga clic en **Guardar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Guarde el archivo. p7b en la unidad de disco duro del servidor y, a continuación, cópielo en una carpeta de cada uno de los servidores perimetrales.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;letra. Exportar con MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;operaciones. Puede exportar el certificado raíz de la CA de cualquier equipo unido al dominio con MMC. Vaya a **Inicio** y **Ejecutar** o abra **Búsqueda** y escriba **MMC** para abrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. En la consola MMC, haga clic en **Archivo** y después haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. En la lista **Agregar o quitar complementos** del cuadro de diálogo elija **Certificados** y luego haga clic en **Agregar**. Cuando aparezca el aviso, seleccione **Cuenta de equipo** y después **Siguiente**. En el diálogo **Seleccionar equipo**, seleccione **Equipo local**. Haga clic en **Finalizar** y después en **Aceptar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cuarta. Expanda **certificados (equipo local)**. Expanda **entidades emisoras de certificados raíz de confianza**. Seleccione **certificados**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Haga clic en el certificado raíz emitido por su CA. Haga clic con el botón derecho en el certificado, seleccione **Todas las tareas** en el menú y después seleccione **Exportar**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. El **Asistente para exportación de certificados** se abre. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. En el diálogo **Formato de archivo de exportación**, elija el formato que desee para exportar. Le recomendamos **Estándar de sintaxis de cifrado de mensajes: certificados PKCS #7 (P7b)**. Si también es su elección, recuerde activar la casilla de verificación **incluir todos los certificados en la ruta de certificación si es posible** , ya que también se exportará la cadena de certificados, incluido el certificado de la entidad emisora raíz y los certificados intermedios. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. En el diálogo **Archivo que se va a exportar**, en la entrada de nombre de archivo, escriba una ruta de acceso y un nombre de archivo (la extensión predeterminada será .p7b) para el certificado exportado. Si le resulta más fácil, seleccione el botón **examinar** para ir a la ubicación en la que desea guardar el certificado exportado y asigne un nombre al certificado exportado. Haga clic en **Guardar**y, a continuación, en **siguiente** cuando esté listo.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Repase el resumen de acciones y haga clic en **Finalizar** para completar la exportación del certificado. Haga clic en **Aceptar** para confirmar si la exportación se ha completado correctamente.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;w.x.y.. Copie el archivo. p7b en cada uno de los servidores perimetrales.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importar la cadena de certificación de la entidad emisora

&nbsp;&nbsp;&nbsp;ninguna. En cada servidor perimetral, abra la consola MMC (elija **iniciar** y **Ejecutar**, o **Buscar**y escriba **MMC** para abrir).
    
&nbsp;&nbsp;&nbsp;letra. En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y después en **Agregar**.
    
&nbsp;&nbsp;&nbsp;c. En el cuadro **Agregar o quitar complementos**, haga clic en **Certificados** y luego en **Agregar**.
    
&nbsp;&nbsp;&nbsp;desarrollo. En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&. En el cuadro de diálogo **Seleccionar equipo**, asegúrese de que la casilla **Equipo local: (el equipo en el que se está ejecutando esta consola)** esté activada y luego haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;f. Haga clic en **Cerrar** y después en **Aceptar**.
    
&nbsp;&nbsp;&nbsp;cuentas. En el árbol de la consola, expanda **Certificados (equipo local)**, haga clic con el botón derecho en **Entidades de certificación raíz de confianza**, vaya a **Todas las tareas** y después haga clic en **Importar**.
    
&nbsp;&nbsp;&nbsp;Prof. En el asistente que aparece, en el cuadro de texto **Archivo para importar**, especifique el nombre de archivo del certificado (el nombre que le ha asignado al archivo .p7b en la sección anterior). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;operaciones. El botón de radio **Colocar todos los certificados en el siguiente almacén, como entidades de certificación raíz de confianza** debería estar seleccionado. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;j. Revise el resumen y haga clic en **Finalizar** para completar la importación.
    
&nbsp;&nbsp;&nbsp;b. Esto debe hacerse para todos los servidores perimetrales que estés implementando.
    
### <a name="3-create-the-certificate-request"></a>3. crear la solicitud de certificado

&nbsp;&nbsp;&nbsp;ninguna. Inicie sesión en uno de los servidores perimetrales, inicie el Asistente para la implementación y en el **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar** (o **vuelva a ejecutar**, si ya ha ejecutado este asistente).
    
&nbsp;&nbsp;&nbsp;letra. En la página **Solicitud de certificado**, asegúrese de que **Certificado de servidor perimetral interno** está seleccionado y haga clic en **Solicitud**.
    
&nbsp;&nbsp;&nbsp;c. En la página **solicitudes demoradas o inmediatas** , elija **enviar la solicitud inmediatamente a una entidad de certificación en línea** si tiene acceso a una desde el entorno perimetral o **preparar la solicitud ahora, pero si no lo hace más adelante,** de otro modo.
    
&nbsp;&nbsp;&nbsp;desarrollo. En la página **Archivo de solicitud de certificado**, escriba la ruta completa y el nombre de archivo de dónde se ha guardado el archivo (como c:\SkypeInternalEdgeCert.cer). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;&. En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**. En caso contrario, no haga nada.
    
&nbsp;&nbsp;&nbsp;f. En la página   Nombre y configuración de seguridad, siga este procedimiento:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;operaciones. En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, servidor perimetral interno).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. En **Longitud de bits**, elija su longitud de bits (el valor predeterminado es 2048, puede ser mayor y ser más segura, pero hará ralentizar el rendimiento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Si necesita un certificado exportable, debe activar la casilla **Marcar la clave privada del certificado como exportable**.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cuarta. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;cuentas. En la página **Información de la organización**, escriba el nombre para la organización y la unidad organizativa (OU). Puede introducir la división o departamento (TI, por ejemplo).
    
&nbsp;&nbsp;&nbsp;Prof. En la página **Información geográfica**, escriba la información de ubicación.
    
&nbsp;&nbsp;&nbsp;operaciones. En la página **Nombre de sujeto/Nombres alternativos de sujeto**, el asistente debe rellenarla automáticamente.
    
&nbsp;&nbsp;&nbsp;j. En la página **Configurar nombres alternativos de sujeto adicionales**, tiene que agregar los nombres alternativos de sujeto adicionales que necesita.
    
&nbsp;&nbsp;&nbsp;b. En la página Resumen de la **solicitud** , revise la información del certificado que se va a usar para generar la solicitud. Si necesita realizar cambios, vuelva atrás y hágalos ahora.
    
&nbsp;&nbsp;&nbsp;cuenta. A continuación, haga clic en **siguiente** para generar el archivo CSR que necesitará proporcionar a la entidad emisora (también puede hacer clic en **Ver registro** para consultar el registro de la solicitud de certificado).
    
&nbsp;&nbsp;&nbsp;unidad. Una vez que se ha generado la solicitud, puede hacer clic en **Ver** para ver el certificado y **Finalizar** para cerrar la ventana. Tiene que darle el contenido del archivo CSR a su CA, para que puedan generar un certificado para importar a este equipo en la siguiente sección.
    

### <a name="4-import-the-certificate"></a>4. importar el certificado

&nbsp;&nbsp;&nbsp;ninguna. Inicie sesión, como miembro del grupo de administradores locales, en el servidor perimetral desde el que realizó la solicitud de certificado en el último procedimiento.
    
&nbsp;&nbsp;&nbsp;letra. En el Asistente para la implementación, junto al **paso 3. Solicitar, instalar o asignar certificados**, **vuelva a**hacer clic en ejecutar.
    
&nbsp;&nbsp;&nbsp;c. En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.
    
&nbsp;&nbsp;&nbsp;desarrollo. En la página **Importar certificado**, escriba la ruta de acceso completa y el nombre de archivo del certificado que obtuvo en la sección anterior (o puede hacer clic en **Examinar** para buscar y seleccionar el archivo de esta forma).
    
&nbsp;&nbsp;&nbsp;&. Si va a importar certificados de otros miembros del grupo de servidores perimetrales y su certificado contiene una clave privada, asegúrese de seleccionar el **archivo de certificado que contiene la clave privada del certificado** y especifique la contraseña. Haga clic en **Siguiente** para continuar.
    
&nbsp;&nbsp;&nbsp;f. En la página**Resumen** , haga clic en **siguiente** una vez que haya confirmado la información y **finalice** una vez que el certificado se haya importado correctamente.
    
 
### <a name="5-export-the-certificate"></a>5. exportar el certificado

&nbsp;&nbsp;&nbsp;ninguna. Asegúrese de que ha iniciado sesión en el servidor perimetral en el que importó el certificado anteriormente, como miembro del grupo de administradores local.
    
&nbsp;&nbsp;&nbsp;letra. Haga clic en **Inicio**, **Ejecutar** (o Abra **Buscar** ) y escriba **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Desde la consola MMC, haga clic en **Archivo** y haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;desarrollo. Desde el cuadro **Agregar o quitar complementos**, haga clic en **Certificados** y en **Agregar**.
    
&nbsp;&nbsp;&nbsp;&. En el cuadro de diálogo **Complementos de certificados**, elija **Cuenta de equipo**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En el diálogo **Seleccionar equipo** seleccione **Equipo local: (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** y la configuración de la consola MMC se ha completado.
    
&nbsp;&nbsp;&nbsp;cuentas. Haga doble clic en **Certificados (equipo local)** para expandir los almacenes de certificados. Haga doble clic en **Personal** y después haga clic en **Certificados**.
    
  > [!NOTE]
  > Es posible que esté aquí y no vea ningún certificado en el almacén personal de certificados para el equipo local. No es necesario que desplace el dedo, si la clave no está allí, el certificado importado no tiene una clave privada asociada. Intente realizar la solicitud e importar los pasos anteriores una vez más y, si está seguro de haber recibido todos los derechos, hable con el administrador o el proveedor de la entidad de certificación. 
  
&nbsp;&nbsp;&nbsp;Prof. En el **almacén personal de certificados** del equipo local, haga clic con el botón secundario en el certificado que va a exportar. Seleccione **Todas las tareas** desde el menú resultante y luego haga clic en **Exportar**.
    
&nbsp;&nbsp;&nbsp;operaciones. En el **Asistente para exportación de certificados**, haga clic en **siguiente**. Seleccione **sí, exportar la clave privada**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;j. En el cuadro de diálogo **Formatos de archivo de exportación**, seleccione **Intercambio de información personal: PKCS#12 (.PFX)** y luego seleccione lo siguiente:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;operaciones. Si es posible, incluir todos los certificados en la ruta de acceso de certificación.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Exportar todas las propiedades extendidas.
    
   > [!NOTE]
   > **NUNCA** seleccione **Eliminar la clave privada si la exportación es correcta**. Significa que debe volver a importar el certificado y la clave privada a este servidor perimetral.
  
&nbsp;&nbsp;&nbsp;b. Si desea asignar una contraseña para proteger la clave privada, puede escribir una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmarla y después haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;cuenta. Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo **.pfx**. Es necesario que los otros servidores perimetrales tengan acceso a la ruta, o bien, tendrá que mover el archivo por medio de medios externos (como una unidad USB). Cuando haya elegido, haga clic en **siguiente** .
    
&nbsp;&nbsp;&nbsp;unidad. Revise el resumen del cuadro de diálogo del **asistente para exportación de certificados** y haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;/n/nel. Haga clic en **Aceptar** en el cuadro de diálogo de exportación correcta.
    
 
### <a name="6-assign-the-certificate"></a>6. asignar el certificado

&nbsp;&nbsp;&nbsp;ninguna. En cada servidor perimetral, en el Asistente para la implementación, junto al **paso 3. Solicitar, instalar o asignar certificados**, **vuelva a**hacer clic en ejecutar.
    
&nbsp;&nbsp;&nbsp;letra. En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Asignación del certificado**, seleccione **Interfaz perimetral interna** en la lista.
    
&nbsp;&nbsp;&nbsp;desarrollo. En la página **almacén de certificados** , seleccione el certificado que ha importado para el contorno interno (de la sección anterior).
    
&nbsp;&nbsp;&nbsp;&. En la página **Resumen de asignación de certificados**, vea la configuración y después haga clic en **Siguiente** para asignar el certificado.
    
&nbsp;&nbsp;&nbsp;f. En la página de finalización del asistente, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;cuentas. Una vez que haya completado este procedimiento, es una buena idea abrir el complemento certificados de MMC en cada servidor perimetral, expandir **certificados (equipo local)**, expandir **personal**, hacer clic en **certificados**y confirmar que el contorno interno el certificado aparece en el panel de detalles.
    
### <a name="external-edge-interface-certificates"></a>Certificados de interfaz de servidor perimetral externo

 
### <a name="1-create-the-certificate-request"></a>1. crear la solicitud de certificado

&nbsp;&nbsp;&nbsp;ninguna. Inicie sesión en uno de los servidores perimetrales, inicie el Asistente para la implementación y en el **paso 3: solicitar, instalar o asignar certificados, haga clic en ejecutar** (o **vuelva a ejecutar**, si ya ha ejecutado este asistente).
    
&nbsp;&nbsp;&nbsp;letra. En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.
    
&nbsp;&nbsp;&nbsp;c. En la página **Solicitud de certificado**, asegúrese de que **Certificado de servidor perimetral externo** está seleccionado y haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;desarrollo. En la página **Solicitudes retrasadas o inmediatas**, haga clic en **Prepare ahora la solicitud, pero envíela más tarde**.
    
&nbsp;&nbsp;&nbsp;&. En la página **Archivo de solicitud de certificado**, escriba la ruta completa y el nombre de archivo de dónde se ha guardado el archivo (como c:\SkypeInternalEdgeCert.cer). Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.
    
&nbsp;&nbsp;&nbsp;cuentas. En la página   Nombre y configuración de seguridad, siga este procedimiento:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;operaciones. En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, servidor perimetral externo).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. En **Longitud de bits**, elija su longitud de bits (el valor predeterminado es 2048, puede ser mayor y ser más segura, pero hará ralentizar el rendimiento).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Si necesita un certificado exportable, debe activar la casilla **Marcar la clave privada del certificado como exportable**.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;cuarta. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;Prof. En la página **Información de la organización**, escriba el nombre para la organización y la unidad organizativa (OU). Puede introducir la división o departamento (TI, por ejemplo).
    
&nbsp;&nbsp;&nbsp;operaciones. En la página **Información geográfica**, escriba la información de ubicación.
    
&nbsp;&nbsp;&nbsp;j. En la página **Nombre de sujeto/Nombres alternativos de sujeto**, el asistente debe rellenar la información necesaria automáticamente.
    
&nbsp;&nbsp;&nbsp;b. En la **opción de configuración de dominio SIP en la página de nombres alternativos de asunto (San)** , active la casilla dominio para agregar un SIP.<sipdomain> entrada a la lista de nombres alternativos de asunto.
    
&nbsp;&nbsp;&nbsp;cuenta. En la página **Configurar nombres alternativos de sujeto adicionales**, tiene que agregar los nombres alternativos de sujeto adicionales que necesita.
    
&nbsp;&nbsp;&nbsp;unidad. En la página Resumen de la **solicitud** , revise la información del certificado que se va a usar para generar la solicitud. Si necesita realizar cambios, vuelva atrás y hágalos ahora.
    
&nbsp;&nbsp;&nbsp;/n/nel. Cuando esté listo, haga clic en **siguiente** para generar el archivo CSR que necesitará proporcionar a la entidad emisora (también puede hacer clic en **Ver registro** para ver el registro de la solicitud de certificado).
    
&nbsp;&nbsp;&nbsp;so. Una vez que se ha generado la solicitud, puede hacer clic en **Ver** para ver el certificado y **Finalizar** para cerrar la ventana. Tiene que darle el contenido del archivo CSR a su CA, para que puedan generar un certificado para importar a este equipo en la siguiente sección.
    
&nbsp;&nbsp;&nbsp;pérdidas. (OPCIONAL) Puede que, al presentar el contenido de la CSR, se le pida cierta información, tal como se muestra a continuación (las CA varían en gran medida, por lo que puede que esto no sea necesario):
    
  - **Microsoft** como la plataforma de servidor
    
  - **IIS** como la versión
    
  - **Web Server** como el tipo de uso
    
  - **PKCS7** como el formato de respuesta
    
 
### <a name="2-import-the-certificate"></a>2. importar el certificado

&nbsp;&nbsp;&nbsp;ninguna. Inicie sesión, como miembro del grupo de administradores locales, en el servidor perimetral desde el que realizó la solicitud de certificado en el último procedimiento.
    
&nbsp;&nbsp;&nbsp;letra. En el Asistente para la implementación, junto al **paso 3. Solicitar, instalar o asignar certificados**, **vuelva a**hacer clic en ejecutar.
    
&nbsp;&nbsp;&nbsp;c. En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.
    
&nbsp;&nbsp;&nbsp;desarrollo. En la página **Importar certificado**, escriba la ruta de acceso completa y el nombre de archivo del certificado que obtuvo en la sección anterior (o puede hacer clic en **Examinar** para buscar y seleccionar el archivo de esta forma). Si su certificado contiene una clave privada, asegúrese de seleccionar **archivo de certificado contiene la clave privada del certificado**y escriba la contraseña de la clave privada. Haga clic en **Siguiente** cuando esté listo.
    
&nbsp;&nbsp;&nbsp;&. En la página **Importar resumen de certificado**, revise el resumen y luego haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En la página **comandos en ejecución** , puede revisar el resultado de la importación cuando se complete haciendo clic en **Ver registro**. Haga clic en **Finalizar** para completar la importación del certificado.
    
&nbsp;&nbsp;&nbsp;cuentas. Si tiene otros servidores perimetrales en un grupo, tendrá que seguir también los dos procedimientos siguientes. Si se trata de un servidor perimetral independiente, está listo para completar los certificados externos.
    
 
### <a name="3-export-the-certificate"></a>3. exportar el certificado

&nbsp;&nbsp;&nbsp;ninguna. Asegúrese de que ha iniciado sesión en el servidor perimetral en el que importó el certificado como administrador local.
    
&nbsp;&nbsp;&nbsp;letra. Haga clic en **Inicio**, **Ejecutar** (o Abra **Buscar** ) y escriba **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Desde la consola MMC, haga clic en **Archivo** y luego haga clic en **Agregar o quitar complemento**.
    
&nbsp;&nbsp;&nbsp;desarrollo. Desde el cuadro **Agregar o quitar complementos**, haga clic en **Certificados** y en **Agregar**.
    
&nbsp;&nbsp;&nbsp;&. En el cuadro de diálogo **Complementos de certificados**, elija **Cuenta de equipo**. Haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;f. En el diálogo **Seleccionar equipo** seleccione **Equipo local: (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** y la configuración de la consola MMC se ha completado.
    
&nbsp;&nbsp;&nbsp;cuentas. Haga doble clic en **Certificados (equipo local)** para expandir los almacenes de certificados. **Haga doble clic en Personal** y después haga clic en **Certificados**.
    
   > [!NOTE]
   > Es posible que esté aquí y no vea ningún certificado en el almacén personal de certificados para el equipo local. No es necesario que desplace el dedo, si la clave no está allí, el certificado importado no tiene una clave privada asociada. Intente realizar la solicitud e importar los pasos anteriores una vez más y, si está seguro de haber recibido todos los derechos, hable con el administrador o el proveedor de la entidad de certificación. 
  
&nbsp;&nbsp;&nbsp;Prof. En el **almacén personal de certificados** del equipo local, haga clic con el botón secundario en el certificado que va a exportar. **Seleccione Todas las tareas** desde el menú resultante y luego haga clic en **Exportar**.
    
&nbsp;&nbsp;&nbsp;operaciones. En el **Asistente para exportación de certificados**, haga clic en **siguiente**. Seleccione **sí, exportar la clave privada**. Haga clic en **Siguiente**.
    
   > [!NOTE]
   > En caso **afirmativo, exportar la clave privada** no está disponible, la clave privada para este certificado no ha sido marcada para su exportación antes de que la recibiera. Tiene que volver a solicitar el certificado del proveedor, con la clave privada establecida en exportar, antes de realizar esto correctamente.
  
&nbsp;&nbsp;&nbsp;j. En el cuadro de diálogo Formatos de archivo de exportación, seleccione Intercambio de información personal: PKCS#12 (.PFX) y luego seleccione lo siguiente:
    
 &nbsp;&nbsp;&nbsp;operaciones. Si es posible, incluir todos los certificados en la ruta de acceso de certificación.
    
 &nbsp;&nbsp;&nbsp;i. Exportar todas las propiedades extendidas.
    
   > [!NOTE]
   > **NUNCA** seleccione **Eliminar la clave privada si la exportación es correcta**. Significa que debe volver a importar el certificado y la clave privada a este servidor perimetral.
  
&nbsp;&nbsp;&nbsp;b. Si desea asignar una contraseña para proteger la clave privada, puede escribir una contraseña para la clave privada. Vuelva a escribir la contraseña para confirmarla y después haga clic en **Siguiente**.
    
&nbsp;&nbsp;&nbsp;cuenta. Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo **.pfx**. Es necesario que los otros servidores perimetrales tengan acceso a la ruta, o bien, tendrá que mover el archivo por medio de medios externos (como una unidad USB). Cuando haya elegido, haga clic en **siguiente** .
    
&nbsp;&nbsp;&nbsp;unidad. Revise el resumen del cuadro de diálogo del **asistente para exportación de certificados** y haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;/n/nel. Haga clic en **Aceptar** en el cuadro de diálogo de exportación correcta.
    
&nbsp;&nbsp;&nbsp;so. Ahora tendrá que volver a la sección importar el certificado antes de esta e importar el certificado a todos los servidores perimetrales restantes y, después, proceder con la asignación, a continuación.
    
 
### <a name="4-assign-the-certificate"></a>4. asignar el certificado

&nbsp;&nbsp;&nbsp;ninguna. En **cada** servidor perimetral, en el Asistente para la implementación, junto al **paso 3. Solicitar, instalar o asignar certificados**, **vuelva a**hacer clic en ejecutar.
    
&nbsp;&nbsp;&nbsp;letra. En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.
    
&nbsp;&nbsp;&nbsp;c. En la página **asignación de certificado** , seleccione **borde externo** en la lista.
    
&nbsp;&nbsp;&nbsp;desarrollo. En la página **almacén de certificados** , seleccione el certificado que ha importado para el contorno externo (de la sección anterior).
    
&nbsp;&nbsp;&nbsp;&. En la página **Resumen de asignación de certificados**, vea la configuración y después haga clic en **Siguiente** para asignar el certificado.
    
&nbsp;&nbsp;&nbsp;f. En la página de finalización del asistente, haga clic en **Finalizar**.
    
&nbsp;&nbsp;&nbsp;cuentas. Una vez que haya completado este procedimiento, es una buena idea abrir el complemento certificados de MMC en cada servidor, expandir **certificados (equipo local)**, expandir **personal**, hacer clic en **certificados**y confirmar que el contorno interno el certificado aparece en el panel de detalles.
    
   > [!NOTE]
   > También tendrá que configurar los certificados para el servidor de proxy inverso. 
  
## <a name="starting-the-edge-servers"></a>Iniciar los servidores perimetrales

Una vez completada la configuración, tendrá que iniciar los servicios en cada servidor perimetral de su implementación:
  
1. En cada servidor perimetral, en el **Asistente**para la implementación, junto al **paso 4: iniciar servicios**, haga clic en **Ejecutar**.
    
2. En la página **iniciar servicios de Skype empresarial Server** , revise la lista de servicios y, a continuación, haga clic en **siguiente** para iniciar los servicios.
    
3. Una vez iniciados los servicios, haga clic en **Finalizar** para cerrar el asistente.
    
4. (Opcional) Aún en el **Paso 4: Iniciar servicios**, haga clic en **Estado de los servicios**.
    
5.  En la **MMC servicios** de cada servidor, compruebe que todos los servicios de Skype empresarial Server se estén ejecutando.
    

