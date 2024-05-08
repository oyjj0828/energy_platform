<template>
    <div style="height:100%; width:100%; display: flex; ">
        <div style="width:25%; height:100%">
            <dv-border-box-13 backgroundColor="rgba(3, 42, 88, .5)" style="left:5%; width:95%; height: 97.5%;">
                <div class="boxall" style="height: 100%">
                    <div class="alltitle">系统信息</div>
                    <div style="position:absolute; top:10%; width:100%; height:90%; display: flex; flex-direction: column;">
                        <div style="flex-grow: 1;">
                            <div style="height:fit-content; width:100%; display:flex; flex-direction:row; justify-content: center;">
                                <span style="text-align: center; width:50%; font-size: 14px; color:#ffffff">光伏装机量</span>
                                <span style="text-align: center; width:50%; font-size: 14px; color:#ffffff">储能装机量</span>
                            </div>
                            <div>

                            </div>
                        </div>

                        <div style="flex-grow: 1;">
                            <div style="height:fit-content; width:100%; display:flex; flex-direction:row; justify-content: center;">
                                <span style="text-align: center; width:100%; font-size: 14px; color:#ffffff">光伏装机量</span>
                            </div>
                        </div>

                        <div style="flex-grow: 1;">
                            <div style="height:fit-content; width:100%; display:flex; flex-direction:row; justify-content: center;">
                                <span style="text-align: center; width:100%; font-size: 14px; color:#ffffff">光伏装机量</span>
                            </div>
                        </div>

                        <div style="flex-grow: 1;">
                            <div style="height:fit-content; width:100%; display:flex; flex-direction:row; justify-content: center;">
                                <span style="text-align: center; width:100%; font-size: 14px; color:#ffffff">光伏装机量</span>
                            </div>
                        </div>

                        <div style="flex-grow: 1;">
                            <div style="height:fit-content; width:100%; display:flex; flex-direction:row; justify-content: center;">
                                <span style="text-align: center; width:100%; font-size: 14px; color:#ffffff">光伏装机量</span>
                            </div>
                        </div>
                        
                        <div style="flex-grow: 1;">
                            <div style="height:fit-content; width:100%; display:flex; flex-direction:row; justify-content: center;">
                                <span style="text-align: center; width:100%; font-size: 14px; color:#ffffff">光伏装机量</span>
                            </div>
                        </div>
                    </div>
                </div>
            </dv-border-box-13>
        </div>
        <div style="width:50%; height:100%; display: flex; flex-direction: column;">
            <div style="height:15%; display:flex">
                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">光伏发电功率</span>
                    <span style="text-align: center; font-size: 14px; color: #ebc30e;">271.33kW</span>
                </div>

                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">充电堆充电功率</span>
                    <span style="text-align: center; font-size: 14px; color: #ebc30e;">200.16kW</span>
                </div>

                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">储能充放电功率</span>
                    <span style="text-align: center; font-size: 14px; color: #ebc30e;">-324.43kW</span>
                </div>
            </div>
            <img src="@/assets/总览.png" style="height:70%"/>
            <div style="height:15%; display:flex">
                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">日供热量</span>
                    <span style="text-align: center; font-size: 14px; color: #0ffb07;">200.16MJ</span>
                </div>
                
                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">日余热回收量</span>
                    <span style="text-align: center; font-size: 14px; color: #0ffb07;">34.16MJ</span>
                </div>

                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">日供冷量</span>
                    <span style="text-align: center; font-size: 14px; color: #0ffb07;">156.78KWh</span>
                </div>

                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">日用水量</span>
                    <span style="text-align: center; font-size: 14px; color: #0ffb07;">35.56m³</span>
                </div>

                <div style="flex-grow: 1; display:flex; flex-direction: column; justify-content: center;">
                    <span style="text-align: center; font-size: 13px; font-weight:bold; color:#ffffff;">日中水处理量</span>
                    <span style="text-align: center; font-size: 14px; color: #0ffb07;">23.89m³</span>
                </div>
            </div>
        </div>
        <div style="width:25%; height:100%; display: flex; flex-direction: column;">
            <dv-border-box-13 backgroundColor="rgba(3, 42, 88, .5)" style="width:95%; height: 44.5%;">
                <div class="boxall" style="height: calc(100% )">
                    <div class="alltitle">告警信息</div>
                </div>
            </dv-border-box-13>
            <div style="height:3%"/>
            <dv-border-box-13 backgroundColor="rgba(3, 42, 88, .5)" style="width:95%; height: 50%;">
                <div class="boxall" style="height: calc(100% )">
                    <div class="alltitle">子系统运行状态</div>
                </div>
            </dv-border-box-13>
        </div>

    </div>
</template>