<script setup lang="ts">
import { ref } from 'vue'

interface ItemProp {
  id: string
  label: string
  type: string
  id_kategori: number
  name_kategori: string
  level: number
  parent_id: string | null
  value: string | null
}

interface Kategori {
  id: number
  nama: string
}

interface Tabel extends Kategori {
  levels: ItemProp[][]
}

const json: ItemProp[] = [
  {
    id: '14',
    label: 'Hilang',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 1,
    parent_id: null,
    value: '7',
  },
  {
    id: '15',
    label: 'Terendam',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 1,
    parent_id: null,
    value: '8',
  },
  {
    id: '16',
    label: 'Hanyut',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 1,
    parent_id: null,
    value: '6',
  },
  {
    id: '39',
    label: 'Rusak',
    type: 'label',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 1,
    parent_id: null,
    value: null,
  },
  {
    id: '43',
    label: 'Luka-Luka',
    type: 'label',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 1,
    parent_id: null,
    value: null,
  },
  {
    id: '13',
    label: 'Meninggal',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 1,
    parent_id: null,
    value: '6',
  },
  {
    id: '53',
    label: 'Kerusakan dan kerugian sosial ekonomi',
    type: 'label',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 1,
    parent_id: null,
    value: null,
  },
  {
    id: '44',
    label: 'Anak-Anak',
    type: 'label',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 2,
    parent_id: '43',
    value: null,
  },
  {
    id: '54',
    label: 'Sawah (Ha)',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '53',
    value: '5',
  },
  {
    id: '46',
    label: 'Lansia',
    type: 'label',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 2,
    parent_id: '43',
    value: null,
  },
  {
    id: '40',
    label: 'Ringan',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '39',
    value: '12',
  },
  {
    id: '41',
    label: 'Sedang',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '39',
    value: '14',
  },
  {
    id: '45',
    label: 'Dewasa',
    type: 'label',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 2,
    parent_id: '43',
    value: null,
  },
  {
    id: '55',
    label: 'Lahan (Ha)',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '53',
    value: '8',
  },
  {
    id: '56',
    label: 'Kebun (Ha)',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '53',
    value: '2',
  },
  {
    id: '57',
    label: 'Kios/Ruko',
    type: 'label',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '53',
    value: null,
  },
  {
    id: '58',
    label: 'Pabrik',
    type: 'label',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '53',
    value: null,
  },
  {
    id: '59',
    label: 'Taksiran Kerugian',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '53',
    value: '10',
  },
  {
    id: '42',
    label: 'Berat',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 2,
    parent_id: '39',
    value: '8',
  },
  {
    id: '65',
    label: 'RR',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 3,
    parent_id: '58',
    value: '4',
  },
  {
    id: '47',
    label: 'Laki-Laki',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 3,
    parent_id: '44',
    value: '7',
  },
  {
    id: '48',
    label: 'Perempuan',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 3,
    parent_id: '44',
    value: '11',
  },
  {
    id: '49',
    label: 'Laki-Laki',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 3,
    parent_id: '45',
    value: '6',
  },
  {
    id: '50',
    label: 'Perempuan',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 3,
    parent_id: '45',
    value: '11',
  },
  {
    id: '51',
    label: 'Laki-Laki',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 3,
    parent_id: '46',
    value: '7',
  },
  {
    id: '52',
    label: 'Perempuan',
    type: 'number',
    id_kategori: 3,
    name_kategori: 'Korban Jiwa',
    level: 3,
    parent_id: '46',
    value: '5',
  },
  {
    id: '60',
    label: 'RB',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 3,
    parent_id: '57',
    value: '3',
  },
  {
    id: '61',
    label: 'RS',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 3,
    parent_id: '57',
    value: '1',
  },
  {
    id: '62',
    label: 'RR',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 3,
    parent_id: '57',
    value: '5',
  },
  {
    id: '63',
    label: 'RB',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 3,
    parent_id: '58',
    value: '3',
  },
  {
    id: '64',
    label: 'RS',
    type: 'number',
    id_kategori: 4,
    name_kategori: 'Kerugian',
    level: 3,
    parent_id: '58',
    value: '2',
  },
]

const list_kategori = ref<Kategori[]>([])
const list_tabel = ref<Tabel[]>([])
const list_value_rows: number[][] = []

for (let i = 0; i < json.length; i += 1) {
  const id_kategori = json[i].id_kategori
  if (!list_kategori.value.find((item) => item.id === id_kategori)) {
    list_kategori.value.push({
      id: id_kategori,
      nama: json[i].name_kategori,
    })
  }
}

for (let i = 0; i < list_kategori.value.length; i += 1) {
  const id_kategori = list_kategori.value[i].id
  const nama_kategori = list_kategori.value[i].nama
  const all_rows = json.filter((item) => item.id_kategori === id_kategori)
  const rows_by_level: ItemProp[][] = []

  const level_number_list: number[] = []
  for (let j = 0; j < all_rows.length; j += 1) {
    const lvl = all_rows[j].level
    if (!level_number_list.includes(lvl)) {
      level_number_list.push(lvl)
    }
  }

  for (let j = 0; j < level_number_list.length; j += 1) {
    const lvl = level_number_list[j]
    const item_level_list = all_rows.filter((r) => r.level === lvl)
    rows_by_level.push(item_level_list)
  }

  const tabel: Tabel = {
    id: id_kategori,
    nama: nama_kategori,
    levels: rows_by_level,
  }
  list_tabel.value.push(tabel)
}

document.body.style.backgroundColor = 'white'
document.body.style.color = 'black'

console.log('LIST TABEL:', list_tabel.value)
</script>

<template>
  <div>Puzzle 1</div>

  <div
    v-for="(kat, i) in list_kategori"
    :key="kat.id"
    style="margin-bottom: 80px"
  >
    <h3 style="text-align: left; margin: 0; margin-bottom: 10px">
      {{ kat.nama }}
    </h3>
    <table :border="1">
      <tr v-for="(levels, j) in list_tabel[i].levels" :key="`tr-${j}`">
        <th v-if="j === 0" :rowspan="levels.length">No.</th>
        <th v-for="(lvl, k) in levels" :key="`tr-${j}-th-${k}`">
          {{ lvl.label }}
        </th>
        <!-- <th rowspan="3">Hilang</th>
        <th colspan="6">Luka-Luka</th>
        <th rowspan="3">Meninggal</th> -->
      </tr>
      <tr>
        <td>1.</td>
        <td
          v-for="(x, j) in Array.from([
            ...list_tabel[i].levels[list_tabel[i].levels.length - 1] as any,
          ]).fill(null)"
        >
          xxx
        </td>
      </tr>
    </table>
  </div>
</template>
