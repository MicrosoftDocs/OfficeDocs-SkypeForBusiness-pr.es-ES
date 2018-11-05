﻿---
title: 'Lync Server 2013: Configuración del proxy inverso para movilidad'
TOCTitle: Configuración del proxy inverso para movilidad
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48275025
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del proxy inverso para movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2014-03-20_

Si desea usar la detección automática de clientes de dispositivos móviles, debe modificar una regla de publicación web o crear una nueva regla de publicación para el proxy inverso tanto si actualiza como si no las listas de nombres alternativos de sujeto en los certificados de proxy inverso.

Si decide usar HTTPS para solicitudes iniciales del servicio Detección automática de Lync Server 2013 y actualizar las listas de nombres alternativos de sujeto en los certificados de proxy inverso, debe asignar el certificado público actualizado a la escucha de la SSL (Capa de sockets seguros) en su proxy inverso. Para obtener información sobre las entradas de nombre alternativo de sujeto requerido, vea [Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). A continuación debe modificar la escucha existente para los servicios web externos o crear una nueva regla de publicación web para la dirección URL externa del servicio Detección automática. Si no tiene una regla de publicación web para la dirección URL de servicios web externos de Lync Server 2013 para su Grupo de servidores front-end, también debe publicar una regla para ella.


> [!NOTE]
> La escucha y la regla de publicación de proxy inverso pueden dar servicio a los servicios web externos y el servicio Detección automática, siempre que el certificado asignado a la escucha contenga el nombre de sujeto necesario y los nombres alternativos de sujeto para ambos. Para obtener detalles sobre la configuración predeterminada de la regla de publicación y el agente de escucha web, vea <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de los servidores proxy inversos para Lync Server 2013</A> para obtener más detalles.



Si decide usar HTTP para solicitudes del servicio Detección automática de manera que no tenga que actualizar nombres alternativos de sujeto para el proxy inverso, debe crear o modificar una nueva regla de publicación web para el puerto 80.

Los procedimientos de esta sección describen cómo crear o modificar las nuevas reglas de publicación web en Microsoft Forefront Threat Management Gateway 2010 para la detección automática.


> [!NOTE]
> Estos procedimientos asumen que ha instalado la Standard Edition de Forefront Threat Management Gateway (TMG) 2010. Si está usando otro proxy inverso, los procedimientos son similares pero tendrán que asignarse a la documentación para el producto de tercero.



## Para crear una regla de publicación web para la dirección URL externa de Detección automática

1.  Haga clic en **Inicio**, diríjase a **Programas**, haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall**, señale **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación de web**, escriba un nombre para mostrar para la regla de publicación (por ejemplo, LyncDiscoveryURL).

4.  En la página **Seleccionar acción de regla**, seleccione **Permitir**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectar al servidor web o la granja de servidores publicados**.

7.  En la página **Detalles internos de publicación**, en **Nombre interno del sitio**, escriba el nombre de dominio completo (FQDN) de su Grupo de directores (por ejemplo, lyncdir01.contoso.local). Si está creando una regla para la URL de servicios web externos en Grupo de servidores front-end, escriba la dirección VIP del equilibrador de carga de hardware (HLB) delante de Grupo de servidores front-end.

8.  En la página **Detalles internos de publicación**, en **Ruta de acceso (opcional)**, escriba **/\*** para la ruta de la carpeta que se va a publicar y, a continuación, haga clic en **Reenviar el encabezado de host original**.

9.  En la página **Detalles de nombre público**, siga este procedimiento:
    
      - En **Aceptar peticiones para**, seleccione **Este nombre de dominio**.
    
      - En **Nombre público**, escriba **lyncdiscover..** *\<sipdomain\>* (la dirección URL externa del servicio Detección automática. Si crea una regla para la dirección URL de servicios web externos en el Grupo de servidores front-end, escriba el FQDN para los servicios web externos en su Grupo de servidores front-end (por ejemplo, lyncwebextpool01.contoso.com).
    
      - En **Ruta de acceso**, escriba **/\*** .

10. En **Seleccionar escucha de web**, en **Escucha**, seleccione su escucha SSL existente con el certificado público actualizado.

11. En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente se puede autenticar directamente**.

12. En la página **Conjunto de usuarios**, seleccione **Todos los usuarios**.

13. En la página **Finalización del Asistente para nueva regla de publicación de web**, compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar**.

14. En la lista de reglas de publicación web de Forefront TMG, haga doble clic en la nueva regla que ha agregado para abrir **Propiedades**.

15. En la pestaña **Para**, realice el siguiente procedimiento:
    
      - Seleccione **Reenviar el encabezado de host original en lugar del real**.
    
      - Seleccione **Las peticiones parecen provenir del equipo de Forefront TMG**.

16. En la pestaña **Protocolo de puente**, configure lo siguiente:
    
      - Seleccione **Servidor web**.
    
      - Seleccione **Redirigir peticiones al puerto HTTP** y escriba **8080** para el número de puerto.
    
      - Seleccione **Redirigir peticiones al puerto SSL** y escriba **4443** para el número de puerto.

17. Haga clic en **Aceptar**.

18. Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

19. Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.

## Para modificar una regla de publicación web existente para agregar la dirección URL y SAN de detección automática

1.  Haga clic en **Inicio**, diríjase a **Programas**, haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.
    
    > [!IMPORTANT]  
    > Repetirá la modificación para cada regla de publicación y escucha que tenga. Normalmente, esta será una regla y escucha para el Grupos de servidores front-end y uno para los grupos de servidores Directores o grupos de Director opcionales, si los ha implementado.
    


2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall** y haga clic en la regla aplicable. En la pestaña **Tareas**, haga clic en **Editar regla seleccionada**.

3.  En la pestaña **Nombre público**, en **Esta regla se aplica a**, seleccione **Peticiones para los sitios web siguientes**.

4.  Haga clic en **Agregar**, escriba el nombre del nuevo sitio de Detección automática (por ejemplo, “lyncdiscover.contoso.com”) y, a continuación, haga clic en **Aceptar**.

5.  En la pestaña **Escucha**, haga clic en **Seleccionar certificado** y asigne el nuevo certificado con las entradas SAN de detección automática agregadas. Cierre las propiedades del agente de escucha y publicación web.

6.  Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

7.  Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.

## Para crear una regla de publicación web para el puerto 80

1.  Haga clic en **Inicio**, diríjase a **Programas**, haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.

2.  En el panel izquierdo, expanda **ServerName**, haga clic con el botón secundario en **Directiva de firewall**, señale **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.

3.  En la página **Asistente para nueva regla de publicación de web**, escriba un nombre para mostrar para la nueva regla de publicación (por ejemplo, Detección automática de Lync (HTTP)).

4.  En la página **Seleccionar acción de regla**, seleccione **Permitir**.

5.  En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.

6.  En la página **Seguridad de conexión de servidor**, seleccione **Usar conexiones no seguras para conectar al servidor web o conjunto de servidores publicado**.

7.  En la página **Detalles internos de publicación**, en **Nombre interno del sitio**, escriba la dirección VIP del equilibrador de carga de hardware (HLB) delante de Grupo de servidores front-end.

8.  En la página **Detalles internos de publicación**, en **Ruta de acceso (opcional)**, escriba **/\*** como la ruta de acceso de la carpeta que se va a publicar y, a continuación, seleccione **Reenviar el encabezado de host original en lugar del especificado en el campo del nombre de sitio interno**.

9.  En la página **Detalles de nombre público**, siga este procedimiento:
    
      - En **Aceptar peticiones para**, seleccione **Este nombre de dominio**.
    
      - En **Nombre público**, escriba **lyncdiscover.** *\<sipdomain\>* (la dirección URL externa del servicio Detección automática.
    
      - En **Ruta de acceso**, escriba **/\*** .

10. En la página **Seleccionar escucha de web**, en **Escucha de web**, seleccione una escucha de web o use el nuevo Asistente para la definición de escucha de web para crear una nueva.

11. En la página **Delegación de autenticación**, seleccione **Sin delegación, y el cliente no se puede autenticar directamente**.

12. En la página **Conjunto de usuarios**, seleccione **Todos los usuarios**.

13. En la página **Finalización del Asistente para nueva regla de publicación de web**, compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar**.

14. En la lista de reglas de publicación web de Forefront TMG, haga doble clic en la nueva regla que ha agregado para abrir **Propiedades**.

15. En la pestaña **Protocolo de puente**, configure lo siguiente:
    
      - Seleccione **Servidor web**.
    
      - Seleccione **Redirigir peticiones al puerto HTTP** y escriba **8080** para el número de puerto.
    
      - Compruebe que **Redirigir peticiones al puerto SSL** no está seleccionado.

16. Haga clic en **Aceptar**.

17. Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.

18. Haga clic en **Probar regla** para comprobar que su nueva regla se ha configurado correctamente.

19. Compruebe que la dirección URL externa del servicio Detección automática no está definida en otra regla de publicación web.

## Vea también

#### Conceptos

[Configuración de los servidores proxy inversos para Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[Requisitos técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)

