<template>
    <div>
        <div id="app" class="main-wrapper">
            <Input v-model="value" type="textarea" :rows="4" placeholder="Enter something..." />
            <im-panel title="单行">
                <im-cell  >   <Button type="primary" @click="showPicker0" long>多列</Button></im-cell>
                <im-cell  >     <Button type="primary"  @click="showPicker1" long>联级</Button></im-cell>
                <im-cell  >    <Button type="primary" @click="showPicker2" long>时间(内置)</Button></im-cell>
                <im-cell  >     <Button type="primary" @click="showPicker3" long>日期(内置)</Button></im-cell>
                <im-cell  >      <Button type="primary" @click="showPicker4" long>区域</Button></im-cell>
            </im-panel>


            <im-picker
                ref="picker0"
                :textTitle="picker0.textTitle"
                :data="picker0.data"
                :anchor="picker0.anchor"
                @confirm="handlePicker0Confirm">
            </im-picker>

            <im-picker
                ref="picker1"
                :textTitle="picker1.textTitle"
                :data="picker1.data"
                :anchor="picker1.anchor"
                @confirm="handlePicker1Confirm">
            </im-picker>

            <im-picker
                ref="picker2"
                :textTitle="picker2.textTitle"
                :type="picker2.type"
                :anchor="picker2.anchor"
                @confirm="handlePicker2Confirm">
            </im-picker>

            <im-picker
                ref="picker3"
                :textTitle="picker3.textTitle"
                :type="picker3.type"
                :anchor="picker3.anchor"
                @confirm="handlePicker3Confirm">
            </im-picker>

            <im-picker
                ref="picker4"
                :textTitle="picker4.textTitle"
                :data="picker4.data"
                :anchor="picker4.anchor"
                @confirm="handlePicker4Confirm">
            </im-picker>
        </div>
    </div>

</template>
<script>
    import areaData from './area.js'
    const data1 = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
    const data2 = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z']

    export default {
        data () {
            return {
                value: null,
                picker0: {
                    anchor: [],
                    textTitle: '多列选择器',
                    data: [data1, data2]
                },
                picker1: {
                    anchor: [],
                    textTitle: '联级选择器',
                    data: [
                        {
                            value: 'A',
                            children: [
                                { value: 'A-a' },
                                { value: 'A-b' },
                                { value: 'A-c' }
                            ]
                        },
                        {
                            value: 'B',
                            children: [
                                { value: 'B-a' },
                                { value: 'B-b' }
                            ]
                        },
                        {
                            value: 'C',
                            children: [
                                { value: 'C-a' },
                                { value: 'C-b' },
                                { value: 'C-c' },
                                { value: 'C-d' }
                            ]
                        },
                        {
                            value: 'D',
                            children: [
                                { value: 'D-a' }
                            ]
                        }
                    ]
                },
                picker2: {
                    anchor: [],
                    textTitle: '时间选择器(内置)',
                    type: 'time'
                },
                picker3: {
                    anchor: [],
                    textTitle: '日期选择器(内置)',
                    type: 'date'
                },
                picker4: {
                    anchor: [],
                    textTitle: '区域选择器',
                    data: areaData
                }
            }
        },
        methods: {
            showPicker0 () {
                this.$refs.picker0.show()
            },
            handlePicker0Confirm (v) {
                this.picker0.anchor = v
                this.value = v ? JSON.stringify(v) : null
            },

            showPicker1 () {
                this.$refs.picker1.show()
            },
            handlePicker1Confirm (v) {
                this.picker1.anchor = v
                this.value = v ? JSON.stringify(v) : null
            },

            showPicker2 () {
                this.$refs.picker2.show()
            },
            handlePicker2Confirm (v) {
                this.picker2.anchor = v
                this.value = v ? JSON.stringify(v) : null
            },

            showPicker3 () {
                this.$refs.picker3.show()
            },
            handlePicker3Confirm (v) {
                this.picker3.anchor = v
                this.value = v ? JSON.stringify(v) : null
            },

            showPicker4 () {
                this.$refs.picker4.show()
            },
            handlePicker4Confirm (v) {
                this.picker4.anchor = v
                this.value = v ? JSON.stringify(v) : null
            }
        }
    }
</script>

<style lang="less">
    body{background: #ededed !important;}
</style>
