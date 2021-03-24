import React, { Component } from "react";
import { Checkbox } from "antd";
const CheckboxGroup = Checkbox.Group;

const plainOptions = ["1", "2", "3"];
const defaultCheckedList = ["1", "2"];

export default class Home extends Component {
	state = {
		checkedList: defaultCheckedList,
		indeterminate: true,
		checkAll: false
	};

	onChange = (checkedList) => {
		this.setState(
			{
				checkedList,
				indeterminate: !!checkedList.length && checkedList.length < plainOptions.length,
				checkAll: checkedList.length === plainOptions.length
			},
			() => {
				this.props.onChange(checkedList);
			}
		);
	};

	onCheckAllChange = (e) => {
		this.setState(
			{
				checkedList: e.target.checked ? plainOptions : [],
				indeterminate: false,
				checkAll: e.target.checked
			},
			() => {
				this.props.onChange(this.state.checkedList);
			}
		);
	};
	render() {
		const { indeterminate, checkAll, checkedList } = this.state;
		return (
			<>
				<Checkbox indeterminate={indeterminate} onChange={this.onCheckAllChange} checked={checkAll}>
					Check all
				</Checkbox>
				<CheckboxGroup value={checkedList} onChange={this.onChange}>
					{this.props.pictures.map((item, index) => {
						return (
							<span key={index}>
								<Checkbox value={item.id} />
								<img src={item.url} />
							</span>
						);
					})}
				</CheckboxGroup>
			</>
		);
	}
}
