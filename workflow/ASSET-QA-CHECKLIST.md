# Asset QA Checklist — outfit / lighting / scene

## A. Wardrobe card

- [ ] 唯一 ID、版本、状态、角色和季节明确。
- [ ] 上下装、外层、内层、配件和鞋履分层清楚。
- [ ] 每个系带、扣具、口袋和挂载有真实固定点。
- [ ] 面料、颜色和厚度有可执行描述。
- [ ] 尾根 / 机械关节 / 散热通道 / 投影接口有明确避让结构。
- [ ] 与前一版本的变化和用户确认依据已记录。
- [ ] 未经用户确认的推断标为候选，不写成锁定事实。

## B. Lighting card / module

- [ ] 主光源有具体位置、方向、色温和作用范围。
- [ ] 补光来源与强度明确，不能覆盖主光方向。
- [ ] 阴影方向、接触阴影和光照衰减合理。
- [ ] 高光落在符合材质与几何关系的位置。
- [ ] 辉光只围绕真实强光源，不抹掉主体细节。
- [ ] 单图特定光照没有被误写成跨项目 STYLE 事实。

## C. Scene / SHOT

- [ ] 一张图只有一个角色、一个动作、一个连续场景。
- [ ] 角色可以专注于活动 / 休息，不强制看镜头。
- [ ] 动作有清楚的承重、接触点和受力关系。
- [ ] 前、中、后景有空间关系，背景不过度堆装饰。
- [ ] 道具数量与动作有关，不为丰富画面而堆叠。
- [ ] 服装按对应卡片执行，不混搭不同系列。
- [ ] 画幅和输出数量符合用户要求；独立图不以拼图替代。

## D. Whale-tail / robot-structure checks

- [ ] DeepSeek 鲸尾从骶尾部正中连接，保留完整双腿，尾鳍水平双叶。
- [ ] 服装开口围绕尾根，不允许从髋侧伸出或穿透完整布料。
- [ ] Yaoyao 的机械关节、检修口和散热通道保持可动 / 可维护。
- [ ] Yaoyao 的数字尾巴明确为非实体投影，不画成生物尾巴。

## E. Scene-state material checks

- [ ] 运动后汗水、水珠和污渍分布符合 `SHOT-MATERIAL-POST-EXERTION`。
- [ ] 泥沙主要在皮肤、膝、小腿和足部，不要无故弄脏整套衣服。
- [ ] 湿发、湿衣、蒸汽和水面反射有明确环境来源。
- [ ] 夜景以指定点光源为主，不能变成全场均匀照明。
- [ ] 正午场景不能误用夕阳色温。

## F. Delivery status

Use only these statuses: `draft`, `design_defined_pending_validation`, `confirmed_constraint`, `candidate`, `validated_single_image`, `review_only_composite`, `superseded`, `not_approved`.

Never mark a design board as a validated illustration. Never count a multi-panel composite as multiple independent outputs.
