---
layout: post
title: Saskatoon Sad Servers
subtitle: Resolución de la máquina Saskatoon de Sad Servers.
header-img: img/in-post/sadservers/saskatoon/header.webp
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - sadservers
  - troubleshoting
  - linux
---
## Escenario

- Tipo: `Do`
- Dificultad: `Easy`
- OS: `Debian 11` 
- Descripción: Hay un archivo de registro de acceso al servidor web en /home/admin/access.log. El archivo consta de una línea por cada petición HTTP, con la dirección IP del solicitante al principio de cada línea. Encuentra cuál es la dirección IP que tiene más peticiones en este archivo (no hay empate; la IP es única). Escribe la solución en el archivo /home/admin/highestip.txt. Por ejemplo, si tu solución es "1.2.3.4", puedes hacer echo "1.2.3.4" > /home/admin/highestip.txt. Prueba: La suma de comprobación SHA1 de la dirección IP sha1sum /home/admin/highestip.txt es 6ef426c40652babc0d081d438b9f353709008e93 (la unica manera de verificar la solución sin desvelarla).
- Tiempo para resolver: 15 minutos.

## Filtrando las direcciones ip.

Para poder hacer un filtrado de las direcciones ocuparemos el siguiente comando, el cual explicare parte por parte.

```bash
grep -o "[0-9]\+\.[0-9]\+\.[0-9]\+\.[0-9]\+" access.log | sort | uniq -c | sort -n
```
## Explicando el comando

### Grep

`grep -o "[0-9]\+\.[0-9]\+\.[0-9]\+\.[0-9]\+" access.log `

Grep es un comando de los sistemas `GNU/Linux`, nos permite realizar busquedas de texto y archivos, en este caso le pasaremos la flag `-o` que nos permite solo hacer match con la cadena que le pasemos, como se puede observar utilizaremos una `REGEX` (expresión regular) en donde indicaremos que solo queremos un rango de `0 a 9` con `[0-9]` y el escape de caracteres `\+` indicamos que queremos unir la busque con otro caracter que sera `.` y eso se le indica con el otro escape de caracteres `\.` dando como resultado `\+\.` ya que despues de los primeros octectos de la ip se encuentan un punto. Y la ultima parte donde se encuenta `access.log` es solo la ruta del archivo.

### Sort 

`sort`

Sort es un comando de `GNU/Linux` que nos permite ordenar texto y archivos de manera interactiva. Sort se diseñó originalmente para su uso con caracteres ASCII. Estas son las reglas por defecto cuando se utiliza la ordenación. Los primeros ejemplos aclararán cómo se gestionan estas prioridades. Luego veremos opciones especializadas: `números > letras > minúsculas > mayúsculas`. En el comando se utilizo una pipe `|` esto quiere decir que despues de la busqueda con grep la salida estandar se concateno con este comando por lo que realizara un ordenamiento a las direcciones IP.

`sort -n`

Es el mismo comando anterior, sin embargo contiene la flag `-n` que compara los datos según los valores numéricos de las cadenas y los ordena. Se utilizo un pipe `|` en el comando puesto que la salida estandar del comando `uniq` que veremos a continuación, se le paso a el `sort -n` para realizar un ordenamiento de la ip con menos registros a la ip con mayor cantidad de visitas registradas.

### Uniq 

`uniq -c`

Uniq es un comando de `GNU/Linux` que Filtrar las líneas adyacentes coincidentes de la ENTRADA (o entrada estándar), y se escriben en OUTPUT (o salida estándar). En el comando se utilizo la flag `-c` ya que esta solo hace un conteo de las lineas de un archivo. Este comando nos ayuda a conocer el numero de visitas de cada ip que contiene el archivo `access.log`

## Obteniendo la IP con mas visitas

La salida del comando es la siguiente:
 
```ruby
      2 182.64.207.187
      2 182.68.184.78
      2 184.154.100.130
      2 184.154.149.126
      2 184.154.15.210
      2 184.154.153.210
      2 184.154.170.122
      2 184.154.88.108
      2 184.185.208.221
      2 184.22.115.74
      2 185.26.239.20
      2 185.38.249.133
      2 185.38.249.96
      2 187.60.96.7
      2 188.176.12.4
      2 188.178.214.179
      2 188.207.200.116
      2 188.240.136.240
      2 190.73.45.219
      2 192.187.119.210
      2 192.227.137.164
      2 192.3.183.199
      2 192.3.22.170
      2 192.99.12.169
      2 193.179.215.103
      2 193.252.118.167
      2 193.252.118.175
      2 193.61.104.6
      2 194.103.63.154
      2 194.254.139.66
      2 194.94.204.181
      2 195.211.162.22
      2 195.38.23.137
      2 198.143.155.251
      2 198.143.156.2
      2 198.167.137.156
      2 198.167.137.193
      2 198.20.79.140
      2 198.50.227.136
      2 198.55.109.202
      2 199.119.124.43
      2 199.30.20.11
      2 199.30.20.161
      2 199.30.20.30
      2 199.30.20.64
      2 199.30.20.65
      2 199.30.20.7
      2 199.30.20.8
      2 199.47.180.6
      2 199.59.148.211
      2 2.0.0.392829
      2 2.51.241.128
      2 2.81967.95841.0
      2 200.89.129.197
      2 202.101.244.118
      2 202.156.10.11
      2 202.232.30.232
      2 203.145.79.41
      2 204.244.74.22
      2 204.93.54.167
      2 204.93.54.173
      2 204.93.54.176
      2 204.93.54.177
      2 204.93.54.238
      2 208.43.255.31
      2 208.50.255.30
      2 212.197.170.45
      2 212.201.44.247
      2 212.48.66.64
      2 212.90.148.107
      2 213.124.13.242
      2 213.52.196.70
      2 213.95.18.125
      2 216.107.155.114
      2 216.151.137.35
      2 216.151.154.100
      2 216.152.243.146
      2 216.152.243.152
      2 216.16.195.52
      2 216.172.140.128
      2 217.119.24.14
      2 217.172.190.158
      2 217.212.224.183
      2 217.69.133.236
      2 218.240.60.244
      2 218.30.103.114
      2 220.241.45.142
      2 23.0.1271.64
      2 23.0.1271.91
      2 23.105.131.185
      2 23.20.83.155
      2 23.92.61.96
      2 23.94.36.245
      2 24.151.226.65
      2 24.196.39.217
      2 33.0.1750.93
      2 37.115.186.244
      2 37.187.101.122
      2 37.188.233.114
      2 37.31.40.234
      2 37.72.189.120
      2 41.251.155.27
      2 46.109.147.195
      2 46.119.121.49
      2 46.165.197.141
      2 46.165.197.151
      2 46.29.8.202
      2 5.10.83.98
      2 5.102.173.71
      2 5.102.48.12
      2 5.135.113.131
      2 5.135.214.254
      2 5.144.176.110
      2 5.144.176.206
      2 5.153.234.2
      2 5.255.72.168
      2 5.255.75.89
      2 5.39.15.151
      2 50.152.223.37
      2 50.180.79.170
      2 50.2.225.180
      2 50.7.50.90
      2 54.219.196.51
      2 54.219.246.6
      2 54.241.62.89
      2 54.242.167.99
      2 54.242.254.219
      2 54.246.137.243
      2 60.29.35.14
      2 61.156.217.135
      2 62.245.76.5
      2 62.4.19.142
      2 63.223.125.175
      2 63.249.66.212
      2 66.249.80.128
      2 66.249.83.223
      2 66.249.83.239
      2 66.249.84.55
      2 66.249.85.135
      2 66.249.88.135
      2 66.249.93.91
      2 67.214.178.190
      2 67.220.144.164
      2 67.220.144.166
      2 67.220.144.226
      2 67.220.144.83
      2 68.65.254.140
      2 69.115.24.125
      2 69.165.204.172
      2 69.167.81.126
      2 69.26.164.70
      2 70.190.77.28
      2 70.210.13.207
      2 71.207.12.53
      2 71.59.29.242
      2 74.125.176.147
      2 74.125.176.83
      2 74.125.19.84
      2 74.125.40.16
      2 74.125.40.20
      2 74.207.228.17
      2 74.221.220.196
      2 74.80.168.244
      2 76.164.234.106
      2 77.125.123.137
      2 77.230.140.4
      2 77.234.68.135
      2 78.128.48.215
      2 78.231.138.213
      2 78.26.132.172
      2 78.46.140.200
      2 78.57.150.9
      2 79.114.20.37
      2 79.118.91.108
      2 79.148.255.215
      2 79.164.36.106
      2 79.170.40.34
      2 79.224.95.124
      2 79.235.40.176
      2 8.35.201.49
      2 8.35.201.53
      2 8.8.178.123
      2 80.123.167.213
      2 80.130.134.87
      2 80.254.166.203
      2 81.130.81.254
      2 81.136.131.79
      2 81.52.143.33
      2 81.56.9.191
      2 82.60.18.23
      2 82.98.148.169
      2 83.115.137.249
      2 83.161.149.61
      2 83.216.183.22
      2 83.252.13.79
      2 83.31.73.148
      2 84.215.206.35
      2 84.58.19.108
      2 85.224.97.187
      2 86.166.162.41
      2 86.19.216.99
      2 86.220.101.19
      2 86.9.201.133
      2 86.96.42.185
      2 87.158.133.11
      2 87.219.103.122
      2 88.172.188.129
      2 88.80.20.186
      2 89.170.74.95
      2 89.44.18.87
      2 90.175.31.133
      2 91.207.8.61
      2 92.100.97.83
      2 92.108.120.46
      2 92.230.101.44
      2 92.237.208.151
      2 92.239.20.53
      2 93.129.45.32
      2 93.203.255.51
      2 94.153.9.168
      2 94.23.106.234
      2 95.108.158.230
      2 95.222.193.200
      2 95.49.190.247
      2 95.91.242.50
      2 96.127.213.6
      2 96.242.86.110
      2 96405.30.17.0
      2 97.74.24.112
      2 98.173.30.75
      2 98.245.87.136
      2 98.85.3.179
      2 99.11.114.240
      2 99.17.221.6
      2 99.237.56.116
      3 1.5.0.11
      3 1.9.1.3
      3 101.199.108.50
      3 107.170.40.197
      3 107.170.40.200
      3 112.216.234.90
      3 113.212.70.121
      3 119.147.146.189
      3 12.43.40.25
      3 130.117.119.80
      3 131.253.24.32
      3 131.253.24.76
      3 14.141.91.20
      3 14.203.126.78
      3 141.89.226.149
      3 15.219.153.83
      3 157.55.33.15
      3 157.55.33.19
      3 157.55.33.88
      3 157.56.229.247
      3 157.56.92.158
      3 157.56.93.154
      3 161.72.16.78
      3 173.192.238.41
      3 173.192.238.58
      3 173.242.120.61
      3 175.143.7.57
      3 180.76.5.214
      3 180.76.5.22
      3 180.76.5.98
      3 180.76.6.28
      3 180.76.6.43
      3 188.165.243.45
      3 193.58.82.178
      3 195.242.218.133
      3 195.250.34.144
      3 198.228.201.147
      3 198.245.61.43
      3 20.0.1132.57
      3 200.49.190.101
      3 201.22.249.225
      3 202.156.10.254
      3 204.236.226.210
      3 205.159.86.10
      3 211.25.11.99
      3 22.0.1190.0
      3 24.0.1290.1
      3 28.0.1500.95
      3 37.115.112.88
      3 46.118.125.84
      3 46.119.119.29
      3 46.161.41.24
      3 5.10.83.105
      3 50.58.161.66
      3 59.90.241.113
      3 65.19.138.34
      3 65.55.215.237
      3 65.55.215.241
      3 68.120.89.142
      3 68.14.231.140
      3 74.125.176.82
      3 74.125.176.84
      3 74.125.19.81
      3 74.125.19.83
      3 74.125.40.17
      3 74.125.40.19
      3 74.125.40.21
      3 74.125.40.22
      3 78.173.140.106
      3 80.108.184.97
      3 82.193.99.33
      3 88.8.30.135
      3 91.9.25.91
      3 93.91.233.50
      3 95.78.54.93
      3 98.206.132.188
      4 103.245.44.13
      4 107.170.40.198
      4 107.170.40.201
      4 107.170.40.203
      4 107.170.40.205
      4 108.170.215.93
      4 122.167.215.241
      4 129.184.84.11
      4 15.211.201.85
      4 157.55.32.190
      4 159.50.249.150
      4 178.19.99.105
      4 178.32.216.134
      4 188.35.22.24
      4 192.95.12.193
      4 198.27.64.9
      4 199.30.20.6
      4 200.10.161.5
      4 204.93.54.178
      4 217.69.133.234
      4 217.69.133.237
      4 217.69.133.70
      4 222.77.201.107
      4 23.229.67.14
      4 24.8.92.137
      4 27.159.203.227
      4 30.0.0.0
      4 31.6.71.243
      4 34.0.1843.0
      4 37.220.7.250
      4 5.10.83.21
      4 5.10.83.53
      4 5.10.83.65
      4 5.10.83.82
      4 50.157.244.41
      4 63.223.125.170
      4 64.237.35.242
      4 65.55.215.37
      4 66.249.81.20
      4 69.160.56.236
      4 74.125.176.145
      4 80.187.96.71
      4 80.237.234.150
      4 80.89.192.53
      4 83.31.36.250
      4 86.28.207.22
      4 88.198.255.242
      4 89.136.142.105
      4 90.1.43.248
      4 98.216.194.189
      5 1.9.2.13
      5 107.170.9.55
      5 108.231.135.74
      5 121.189.37.60
      5 157.56.92.151
      5 166.147.88.15
      5 178.172.239.240
      5 195.160.233.249
      5 195.248.32.227
      5 198.228.201.171
      5 203.173.241.145
      5 207.45.249.135
      5 217.174.111.254
      5 217.212.224.181
      5 217.69.133.238
      5 24.115.69.95
      5 24.5.221.92
      5 24.97.227.132
      5 26.0.1410.58
      5 37.194.3.12
      5 42.107.175.146
      5 49.206.120.190
      5 5.10.83.23
      5 5.10.83.91
      5 50.132.55.62
      5 54.220.160.83
      5 59.124.42.160
      5 65.19.138.33
      5 65.52.104.233
      5 67.233.210.41
      5 71.212.224.97
      5 74.105.15.185
      5 74.125.19.80
      5 81.154.31.181
      5 82.136.45.164
      5 82.165.139.53
      5 84.121.6.23
      5 85.170.84.143
      5 87.64.176.135
      5 91.232.96.8
      5 93.152.153.38
      5 93.57.95.188
      5 98.248.53.169
      5 99.101.69.97
      6 1.22.35.226
      6 100.2.4.116
      6 105.235.130.196
      6 105.235.218.242
      6 106.51.250.126
      6 106.79.29.147
      6 107.170.40.199
      6 107.203.4.32
      6 108.15.20.23
      6 108.28.155.98
      6 108.29.33.122
      6 109.189.132.223
      6 109.190.148.218
      6 109.195.177.171
      6 109.231.204.82
      6 110.136.166.128
      6 112.202.18.45
      6 114.69.226.80
      6 115.112.80.98
      6 115.114.17.146
      6 116.203.238.137
      6 116.50.181.5
      6 117.195.177.223
      6 117.227.171.181
      6 118.72.253.84
      6 119.6.7.18
      6 120.59.2.54
      6 121.209.208.128
      6 125.122.211.40
      6 125.199.63.98
      6 128.179.155.97
      6 130.126.255.121
      6 130.229.158.194
      6 130.239.41.58
      6 134.192.71.41
      6 134.58.253.57
      6 14.18.25.243
      6 141.142.223.45
      6 147.142.186.54
      6 150.101.171.78
      6 155.201.35.55
      6 155.63.71.11
      6 157.127.239.146
      6 160.92.7.69
      6 162.211.96.55
      6 162.44.252.21
      6 163.157.254.25
      6 166.37.114.52
      6 17.0.963.79
      6 173.164.44.34
      6 173.166.158.222
      6 173.36.196.6
      6 174.23.200.134
      6 174.26.93.238
      6 174.51.6.146
      6 174.93.161.163
      6 176.14.63.246
      6 177.132.188.205
      6 177.141.70.11
      6 177.6.142.6
      6 177.73.254.10
      6 178.118.111.33
      6 178.15.11.82
      6 178.152.18.59
      6 178.17.6.226
      6 178.213.66.2
      6 178.32.51.157
      6 179.179.206.176
      6 180.166.130.86
      6 181.160.193.212
      6 182.253.23.3
      6 183.221.90.177
      6 183.87.253.120
      6 184.153.164.52
      6 184.60.23.120
      6 186.22.52.72
      6 188.205.61.177
      6 188.250.157.192
      6 188.80.229.128
      6 189.11.65.66
      6 189.214.42.128
      6 189.71.37.115
      6 19.0.1326.59
      6 190.198.191.75
      6 190.82.255.69
      6 193.146.92.166
      6 193.167.195.60
      6 193.185.55.253
      6 193.225.194.254
      6 193.238.231.119
      6 193.252.149.222
      6 193.30.41.222
      6 193.40.6.84
      6 193.77.124.16
      6 193.77.158.208
      6 194.105.145.147
      6 194.14.211.19
      6 194.146.132.138
      6 194.171.252.104
      6 194.45.150.17
      6 195.176.191.93
      6 195.250.51.10
      6 195.44.196.178
      6 195.56.119.209
      6 196.14.132.154
      6 197.36.142.40
      6 198.148.112.117
      6 199.204.56.18
      6 199.247.189.63
      6 2.0.9.20
      6 2.137.32.153
      6 200.68.86.233
      6 200.85.183.174
      6 201.124.21.149
      6 201.76.90.77
      6 202.68.209.129
      6 203.122.224.39
      6 203.206.205.64
      6 203.219.2.2
      6 203.41.198.36
      6 203.84.135.120
      6 207.255.245.133
      6 208.54.40.237
      6 209.118.149.82
      6 210.71.251.31
      6 211.9.44.193
      6 212.159.68.200
      6 212.180.233.101
      6 212.242.185.85
      6 213.112.253.123
      6 213.150.233.62
      6 213.17.226.11
      6 213.174.192.220
      6 213.181.52.10
      6 213.193.72.155
      6 213.21.42.46
      6 213.252.7.178
      6 217.140.110.23
      6 217.91.18.234
      6 218.188.93.140
      6 220.209.87.113
      6 220.244.10.116
      6 220.245.217.154
      6 24.0.1312.52
      6 24.130.53.65
      6 24.147.91.100
      6 24.21.55.63
      6 25.0.1364.152
      6 25.0.1364.172
      6 3.0.04506.30
      6 3.2.1.25875
      6 3.2.17.1009776
      6 30.0.1599.66
      6 30.0.1599.69
      6 31.35.64.245
      6 31.4.197.143
      6 32.0.1678.0
      6 36.38.8.174
      6 37.115.113.172
      6 41.74.172.23
      6 46.118.127.106
      6 46.33.196.184
      6 46.4.101.88
      6 46.65.248.177
      6 5.102.10.173
      6 5.56.158.218
      6 50.103.242.61
      6 50.59.104.212
      6 54.255.13.204
      6 59.124.251.135
      6 61.12.113.192
      6 61.135.169.84
      6 61.16.241.98
      6 61.246.186.198
      6 62.12.14.27
      6 62.159.237.82
      6 62.159.77.167
      6 62.192.67.154
      6 62.44.32.116
      6 62.47.98.178
      6 62.50.6.113
      6 64.134.102.242
      6 64.237.51.169
      6 64.80.110.74
      6 65.172.240.122
      6 66.187.233.202
      6 66.211.105.190
      6 67.253.133.120
      6 67.61.162.49
      6 68.13.110.158
      6 68.151.4.139
      6 68.174.223.12
      6 68.183.65.140
      6 68.184.202.186
      6 68.88.73.113
      6 69.181.104.228
      6 69.234.185.154
      6 69.85.215.56
      6 70.109.45.64
      6 70.112.152.59
      6 70.127.254.161
      6 70.182.103.221
      6 70.186.197.197
      6 71.191.158.163
      6 71.207.215.148
      6 71.33.204.157
      6 71.9.98.194
      6 72.174.22.174
      6 72.199.66.220
      6 72.215.249.101
      6 72.4.104.94
      6 72.54.172.193
      6 72.9.0.86
      6 74.125.176.148
      6 74.125.176.149
      6 74.218.234.48
      6 74.76.53.142
      6 75.132.156.143
      6 75.134.169.174
      6 75.161.167.75
      6 76.103.82.13
      6 76.115.204.132
      6 76.14.236.249
      6 76.167.133.189
      6 77.0.42.68
      6 77.1.77.21
      6 77.11.205.74
      6 77.175.189.215
      6 77.175.4.43
      6 77.240.31.230
      6 77.248.77.178
      6 78.145.242.171
      6 78.19.193.147
      6 78.6.176.46
      6 78.97.239.35
      6 79.185.184.23
      6 79.191.201.108
      6 79.197.82.119
      6 79.35.84.239
      6 79.83.255.199
      6 80.133.249.216
      6 80.153.191.173
      6 80.156.209.18
      6 80.239.169.204
      6 80.252.78.170
      6 80.28.130.108
      6 80.48.102.35
      6 80.57.170.121
      6 81.142.35.154
      6 81.157.147.252
      6 81.170.148.153
      6 81.210.53.2
      6 81.220.24.207
      6 81.61.214.106
      6 82.130.48.164
      6 82.130.49.223
      6 82.145.208.98
      6 82.145.219.13
      6 82.233.80.245
      6 82.247.137.135
      6 83.105.90.45
      6 83.175.127.2
      6 83.206.120.18
      6 83.69.235.12
      6 84.112.29.184
      6 84.233.151.236
      6 84.46.60.57
      6 84.60.79.43
      6 85.216.186.139
      6 85.248.108.8
      6 85.254.143.114
      6 85.28.124.249
      6 86.1.76.62
      6 86.182.52.145
      6 86.56.94.63
      6 87.182.248.236
      6 87.216.109.88
      6 87.6.86.34
      6 88.196.179.78
      6 88.210.182.128
      6 88.218.141.221
      6 89.121.200.106
      6 89.156.153.83
      6 89.212.62.88
      6 89.238.251.138
      6 89.250.16.2
      6 90.220.199.149
      6 91.151.182.109
      6 91.177.205.119
      6 91.179.36.136
      6 91.180.146.16
      6 91.183.139.98
      6 91.213.10.2
      6 91.220.39.15
      6 91.231.179.253
      6 91.68.55.56
      6 91.99.29.38
      6 92.115.179.247
      6 92.163.85.51
      6 92.230.229.41
      6 92.236.181.94
      6 92.50.146.166
      6 93.114.45.13
      6 93.139.195.61
      6 93.191.160.193
      6 93.210.154.199
      6 93.80.29.12
      6 94.222.112.110
      6 94.23.164.135
      6 95.148.254.71
      6 95.172.74.38
      6 95.82.59.254
      6 95.87.197.134
      6 95.97.244.106
      6 96.254.233.150
      6 96.36.44.80
      6 96.63.29.108
      6 97.116.185.190
      6 98.193.68.66
      6 98.210.187.48
      6 98.227.31.237
      6 99.158.0.150
      6 99.171.108.193
      6 99.6.61.4
      7 107.170.40.204
      7 108.91.82.251
      7 109.167.131.110
      7 109.74.154.79
      7 111.240.183.248
      7 114.141.164.18
      7 115.77.7.145
      7 116.75.148.149
      7 117.28.234.67
      7 118.169.39.21
      7 118.97.174.156
      7 119.36.179.179
      7 12.110.81.190
      7 122.146.177.66
      7 128.147.28.1
      7 128.61.85.15
      7 128.61.92.96
      7 129.70.212.93
      7 130.226.230.7
      7 132.229.223.2
      7 138.96.204.237
      7 151.225.221.231
      7 176.226.17.33
      7 183.37.131.40
      7 185.2.138.125
      7 189.170.95.135
      7 193.104.184.225
      7 193.24.88.211
      7 194.149.247.24
      7 194.249.247.164
      7 194.250.79.71
      7 195.14.103.53
      7 195.14.72.29
      7 195.194.187.106
      7 195.228.139.91
      7 199.16.156.124
      7 202.59.2.2
      7 202.86.115.186
      7 203.219.136.224
      7 206.47.94.142
      7 208.43.255.27
      7 208.43.255.28
      7 209.141.128.208
      7 212.33.34.196
      7 212.84.56.58
      7 213.10.136.118
      7 213.160.109.10
      7 213.61.156.100
      7 216.109.99.4
      7 216.143.11.118
      7 217.116.157.26
      7 217.17.193.66
      7 26.0.1410.64
      7 27.251.237.154
      7 46.5.254.123
      7 50.131.220.143
      7 50.8.159.176
      7 62.134.44.20
      7 62.77.171.249
      7 65.55.213.79
      7 67.244.81.209
      7 68.180.224.235
      7 72.76.128.176
      7 75.67.42.229
      7 76.176.53.173
      7 76.2.185.161
      7 78.193.126.4
      7 78.49.133.207
      7 79.176.36.151
      7 80.118.116.26
      7 81.34.53.43
      7 82.135.32.98
      7 82.181.180.138
      7 83.221.67.237
      7 83.253.123.163
      7 84.52.150.17
      7 84.75.200.115
      7 85.89.160.218
      7 88.184.51.134
      7 89.191.52.88
      7 89.216.30.194
      7 89.238.233.38
      7 91.114.206.13
      7 91.204.25.44
      7 92.234.93.242
      7 94.228.34.233
      7 94.253.195.219
      7 94.7.95.97
      7 96.49.214.84
      8 106.187.34.32
      8 109.74.151.149
      8 110.159.23.90
      8 110.170.125.5
      8 128.214.173.46
      8 134.76.249.10
      8 155.140.133.248
      8 170.148.69.141
      8 177.106.12.201
      8 184.162.26.147
      8 187.45.193.158
      8 188.192.27.241
      8 188.9.138.189
      8 190.153.25.242
      8 192.44.32.8
      8 193.50.193.83
      8 193.83.204.66
      8 199.16.156.126
      8 208.43.243.244
      8 212.39.97.114
      8 216.14.198.50
      8 24.237.38.218
      8 27.0.1453.93
      8 30.0.1599.114
      8 33.0.1750.5
      8 50.158.157.89
      8 63.140.98.80
      8 64.131.102.243
      8 74.125.176.151
      8 81.187.167.236
      8 89.68.134.81
      9 130.243.172.179
      9 139.184.30.132
      9 143.233.204.28
      9 173.11.136.157
      9 199.16.156.125
      9 207.241.237.221
      9 208.43.251.180
      9 216.14.102.16
      9 24.0.1309.0
      9 31.208.44.206
      9 32.0.1700.103
      9 67.170.98.63
      9 69.167.130.5
      9 74.125.176.144
      9 74.125.176.146
      9 78.171.202.100
      9 80.160.68.134
      9 80.32.77.152
      9 84.137.208.44
      9 85.168.225.197
      9 85.43.182.12
      9 86.130.160.107
      9 91.236.75.25
      9 94.7.215.43
      9 97.82.80.65
      9 98.122.171.175
      9 99.33.244.41
     10 1.9.0.19
     10 106.51.144.106
     10 107.170.41.69
     10 110.184.146.254
     10 120.202.255.147
     10 132.252.139.85
     10 150.101.192.144
     10 178.203.37.192
     10 24.84.241.107
     10 32.0.1700.76
     10 68.4.202.231
     10 74.125.176.150
     10 77.241.193.88
     10 98.252.226.135
     11 207.241.237.103
     11 207.241.237.226
     11 74.125.19.82
     11 75.144.62.181
     11 88.112.19.251
     12 176.31.103.52
     12 194.126.102.178
     12 207.241.237.224
     12 26.0.1410.43
     12 33.0.1750.58
     12 33.0.1750.70
     12 34.0.1833.5
     12 66.162.222.50
     12 66.6.147.80
     12 79.103.41.39
     12 84.85.130.133
     12 89.218.93.74
     12 94.79.44.40
     13 173.231.106.34
     13 186.231.123.210
     13 188.122.8.79
     13 192.118.118.1
     13 193.33.2.113
     13 207.241.237.102
     13 207.241.237.104
     13 207.241.237.225
     13 37.11.0.8
     13 66.249.81.91
     14 108.32.74.68
     14 19.0.1326.63
     14 194.29.137.5
     14 49.204.238.249
     14 81.198.20.11
     15 14.141.56.98
     15 146.1.1.2
     15 30.0.1599.101
     16 207.241.237.228
     16 218.30.103.62
     16 79.101.87.86
     17 178.255.215.71
     17 207.241.237.101
     17 207.241.237.227
     17 31.0.1650.57
     17 50.131.51.216
     17 78.157.154.210
     17 93.104.161.108
     18 106.78.19.160
     18 201.26.152.202
     18 207.241.237.220
     18 6.2.3.3
     18 72.223.76.198
     18 79.84.40.134
     18 83.42.229.238
     18 89.2.87.1
     19 208.93.0.48
     19 29.0.1547.76
     19 81.190.174.219
     19 91.221.131.30
     20 185.4.253.67
     21 207.241.237.223
     22 178.255.215.83
     22 32.0.1700.21
     22 70.83.251.183
     23 108.174.55.234
     23 150.162.56.185
     23 176.92.75.62
     23 217.195.202.13
     23 83.149.9.216
     23 88.103.19.195
     24 94.93.82.148
     25 216.152.249.242
     25 217.12.185.5
     26 222.14.252.108
     26 83.61.80.53
     26 99.252.100.83
     27 134.158.231.20
     27 144.76.95.39
     27 212.51.173.12
     27 34.0.1838.2
     28 23.30.147.145
     29 65.55.213.74
     29 82.80.14.189
     29 88.120.89.50
     32 128.118.108.67
     32 2.241.35.167
     32 208.43.251.181
     32 24.0.194.37
     32 61.140.183.41
     33 101.119.18.35
     33 14.140.163.52
     33 194.186.207.105
     33 219.64.34.68
     33 38.99.236.50
     33 62.225.70.202
     33 79.171.127.34
     33 80.108.25.232
     33 85.115.58.180
     33 88.3.37.62
     34 122.166.142.108
     34 200.31.173.106
     34 203.99.205.107
     34 204.62.56.3
     34 32.0.1700.77
     35 193.244.33.47
     36 23.0.1271.95
     37 111.199.235.239
     37 184.66.149.103
     37 89.107.177.18
     38 24.11.96.184
     38 67.61.65.249
     39 115.112.233.75
     39 27.0.1453.110
     39 59.163.27.11
     40 209.17.114.78
     40 210.13.83.18
     41 144.76.194.187
     41 183.179.22.186
     41 199.168.96.66
     41 34.0.1825.4
     42 208.43.252.200
     43 93.17.51.134
     50 14.160.65.22
     50 86.76.247.183
     52 50.139.66.106
     56 66.249.73.185
     60 208.91.156.11
     60 25.0.1364.160
     60 65.55.213.73
     65 1.8.1.4
     65 108.171.116.194
     65 2.0.0.4
     65 3.0.4506.2152
     68 32.0.1700.99
     74 208.115.113.88
     82 198.46.149.143
     83 208.115.111.72
     84 100.43.83.137
     91 19.0.1084.52
     97 31.0.1650.63
     99 68.180.224.225
    102 209.85.238.199
    113 50.16.19.13
    273 75.97.9.59
    335 32.0.1700.102
    357 130.237.218.86
    364 46.105.14.53
    465 33.0.1750.91
    482 66.249.73.135
   1894 32.0.1700.107
```
## ¿Error con el comando?
Por alguna razón la ip con mas visitas registradas deberia ser `32.0.1700.106` con `1894` registros, pero como podemos observar los octetos de la ip estan mal, ya que solo deberian tener 3 bits por octeto y nos encontramos con `1700` en el tercer octeto. Por lo que no es siquiera una ip valida para IPV4.

## Verificando con hash

Como mencione antes, la ip `32.0.1700.107` queda descartada, pero igualmente haremos la comprobación, el has esperado deberia ser `6ef426c40652babc0d081d438b9f353709008e93` y como se puede observar no coincide.

```ruby
admin@ip-172-31-27-155:~$ sha1sum highestip.txt 
0de411a22db0ab346a18aee0feccdfb40dbd57a0  highestip.txt
```
Ahora comprobaremos con `66.249.73.135` y como se puede observar el has coincide con el que nos otorgo sadservers.


```ruby
admin@ip-172-31-27-155:~$ sha1sum highestip.txt
6ef426c40652babc0d081d438b9f353709008e93  highestip.txt
```
## Escribiendo la solución
Para que la solución sea valida es necesario escribirla en el archivo `/home/admin/highestip.txt` asi que usaremos un echo para hacerlo.

```bash
echo "66.249.73.135" > highestip.txt
```

## Resultado

Y listo, tenemos la maquina resuelta.

![solución](/img/in-post/sadservers/saskatoon/solution.webp) 

Eso ha sido todo por el post, si piensas que me he equivocado en algo o que he omitido alguna parte, hazmelo saber en discord `quantumwavves`