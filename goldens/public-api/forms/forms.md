## API Report File for "@angular/forms"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { AfterViewInit } from '@angular/core';
import { ElementRef } from '@angular/core';
import { EventEmitter } from '@angular/core';
import { InjectionToken } from '@angular/core';
import { Injector } from '@angular/core';
import { ModuleWithProviders } from '@angular/core';
import { Observable } from 'rxjs';
import { OnChanges } from '@angular/core';
import { OnDestroy } from '@angular/core';
import { OnInit } from '@angular/core';
import { Renderer2 } from '@angular/core';
import { SimpleChanges } from '@angular/core';
import { Version } from '@angular/core';

// @public
export abstract class AbstractControl {
    constructor(validators: ValidatorFn | ValidatorFn[] | null, asyncValidators: AsyncValidatorFn | AsyncValidatorFn[] | null);
    addAsyncValidators(validators: AsyncValidatorFn | AsyncValidatorFn[]): void;
    addValidators(validators: ValidatorFn | ValidatorFn[]): void;
    get asyncValidator(): AsyncValidatorFn | null;
    set asyncValidator(asyncValidatorFn: AsyncValidatorFn | null);
    clearAsyncValidators(): void;
    clearValidators(): void;
    get dirty(): boolean;
    disable(opts?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    get disabled(): boolean;
    enable(opts?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    get enabled(): boolean;
    readonly errors: ValidationErrors | null;
    get(path: Array<string | number> | string): AbstractControl | null;
    getError(errorCode: string, path?: Array<string | number> | string): any;
    hasAsyncValidator(validator: AsyncValidatorFn): boolean;
    hasError(errorCode: string, path?: Array<string | number> | string): boolean;
    hasValidator(validator: ValidatorFn): boolean;
    get invalid(): boolean;
    markAllAsTouched(): void;
    markAsDirty(opts?: {
        onlySelf?: boolean;
    }): void;
    markAsPending(opts?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    markAsPristine(opts?: {
        onlySelf?: boolean;
    }): void;
    markAsTouched(opts?: {
        onlySelf?: boolean;
    }): void;
    markAsUntouched(opts?: {
        onlySelf?: boolean;
    }): void;
    get parent(): FormGroup | FormArray | null;
    abstract patchValue(value: any, options?: Object): void;
    get pending(): boolean;
    readonly pristine: boolean;
    removeAsyncValidators(validators: AsyncValidatorFn | AsyncValidatorFn[]): void;
    removeValidators(validators: ValidatorFn | ValidatorFn[]): void;
    abstract reset(value?: any, options?: Object): void;
    get root(): AbstractControl;
    setAsyncValidators(validators: AsyncValidatorFn | AsyncValidatorFn[] | null): void;
    setErrors(errors: ValidationErrors | null, opts?: {
        emitEvent?: boolean;
    }): void;
    // (undocumented)
    setParent(parent: FormGroup | FormArray): void;
    setValidators(validators: ValidatorFn | ValidatorFn[] | null): void;
    abstract setValue(value: any, options?: Object): void;
    readonly status: FormControlStatus;
    readonly statusChanges: Observable<FormControlStatus>;
    readonly touched: boolean;
    get untouched(): boolean;
    get updateOn(): FormHooks;
    updateValueAndValidity(opts?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    get valid(): boolean;
    get validator(): ValidatorFn | null;
    set validator(validatorFn: ValidatorFn | null);
    readonly value: any;
    readonly valueChanges: Observable<any>;
}

// @public
export abstract class AbstractControlDirective {
    get asyncValidator(): AsyncValidatorFn | null;
    abstract get control(): AbstractControl | null;
    get dirty(): boolean | null;
    get disabled(): boolean | null;
    get enabled(): boolean | null;
    get errors(): ValidationErrors | null;
    getError(errorCode: string, path?: Array<string | number> | string): any;
    hasError(errorCode: string, path?: Array<string | number> | string): boolean;
    get invalid(): boolean | null;
    get path(): string[] | null;
    get pending(): boolean | null;
    get pristine(): boolean | null;
    reset(value?: any): void;
    get status(): string | null;
    get statusChanges(): Observable<any> | null;
    get touched(): boolean | null;
    get untouched(): boolean | null;
    get valid(): boolean | null;
    get validator(): ValidatorFn | null;
    get value(): any;
    get valueChanges(): Observable<any> | null;
}

// @public
export interface AbstractControlOptions {
    asyncValidators?: AsyncValidatorFn | AsyncValidatorFn[] | null;
    updateOn?: 'change' | 'blur' | 'submit';
    validators?: ValidatorFn | ValidatorFn[] | null;
}

// @public
export class AbstractFormGroupDirective extends ControlContainer implements OnInit, OnDestroy {
    get control(): FormGroup;
    get formDirective(): Form | null;
    // (undocumented)
    ngOnDestroy(): void;
    // (undocumented)
    ngOnInit(): void;
    get path(): string[];
}

// @public
export interface AsyncValidator extends Validator {
    validate(control: AbstractControl): Promise<ValidationErrors | null> | Observable<ValidationErrors | null>;
}

// @public
export interface AsyncValidatorFn {
    // (undocumented)
    (control: AbstractControl): Promise<ValidationErrors | null> | Observable<ValidationErrors | null>;
}

// @public
export class CheckboxControlValueAccessor extends ɵangular_packages_forms_forms_g implements ControlValueAccessor {
    writeValue(value: any): void;
}

// @public
export class CheckboxRequiredValidator extends RequiredValidator {
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export const COMPOSITION_BUFFER_MODE: InjectionToken<boolean>;

// @public
export abstract class ControlContainer extends AbstractControlDirective {
    get formDirective(): Form | null;
    name: string | number | null;
    get path(): string[] | null;
}

// @public
export interface ControlValueAccessor {
    registerOnChange(fn: any): void;
    registerOnTouched(fn: any): void;
    setDisabledState?(isDisabled: boolean): void;
    writeValue(obj: any): void;
}

// @public
export class DefaultValueAccessor extends ɵangular_packages_forms_forms_f implements ControlValueAccessor {
    constructor(renderer: Renderer2, elementRef: ElementRef, _compositionMode: boolean);
    writeValue(value: any): void;
}

// @public
export class EmailValidator implements Validator {
    set email(value: boolean | string);
    registerOnValidatorChange(fn: () => void): void;
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export interface Form {
    addControl(dir: NgControl): void;
    addFormGroup(dir: AbstractFormGroupDirective): void;
    getControl(dir: NgControl): FormControl;
    getFormGroup(dir: AbstractFormGroupDirective): FormGroup;
    removeControl(dir: NgControl): void;
    removeFormGroup(dir: AbstractFormGroupDirective): void;
    updateModel(dir: NgControl, value: any): void;
}

// @public
export class FormArray extends AbstractControl {
    constructor(controls: AbstractControl[], validatorOrOpts?: ValidatorFn | ValidatorFn[] | AbstractControlOptions | null, asyncValidator?: AsyncValidatorFn | AsyncValidatorFn[] | null);
    at(index: number): AbstractControl;
    clear(options?: {
        emitEvent?: boolean;
    }): void;
    // (undocumented)
    controls: AbstractControl[];
    getRawValue(): any[];
    insert(index: number, control: AbstractControl, options?: {
        emitEvent?: boolean;
    }): void;
    get length(): number;
    patchValue(value: any[], options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    push(control: AbstractControl, options?: {
        emitEvent?: boolean;
    }): void;
    removeAt(index: number, options?: {
        emitEvent?: boolean;
    }): void;
    reset(value?: any, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    setControl(index: number, control: AbstractControl, options?: {
        emitEvent?: boolean;
    }): void;
    setValue(value: any[], options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
}

// @public
export class FormArrayName extends ControlContainer implements OnInit, OnDestroy {
    constructor(parent: ControlContainer, validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[]);
    get control(): FormArray;
    get formDirective(): FormGroupDirective | null;
    name: string | number | null;
    ngOnDestroy(): void;
    ngOnInit(): void;
    get path(): string[];
}

// @public
export class FormBuilder {
    array(controlsConfig: any[], validatorOrOpts?: ValidatorFn | ValidatorFn[] | AbstractControlOptions | null, asyncValidator?: AsyncValidatorFn | AsyncValidatorFn[] | null): FormArray;
    control(formState: any, validatorOrOpts?: ValidatorFn | ValidatorFn[] | AbstractControlOptions | null, asyncValidator?: AsyncValidatorFn | AsyncValidatorFn[] | null): FormControl;
    group(controlsConfig: {
        [key: string]: any;
    }, options?: AbstractControlOptions | null): FormGroup;
    // @deprecated
    group(controlsConfig: {
        [key: string]: any;
    }, options: {
        [key: string]: any;
    }): FormGroup;
}

// @public
export class FormControl extends AbstractControl {
    constructor(formState?: any, validatorOrOpts?: ValidatorFn | ValidatorFn[] | AbstractControlOptions | null, asyncValidator?: AsyncValidatorFn | AsyncValidatorFn[] | null);
    patchValue(value: any, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
        emitModelToViewChange?: boolean;
        emitViewToModelChange?: boolean;
    }): void;
    registerOnChange(fn: Function): void;
    registerOnDisabledChange(fn: (isDisabled: boolean) => void): void;
    reset(formState?: any, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    setValue(value: any, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
        emitModelToViewChange?: boolean;
        emitViewToModelChange?: boolean;
    }): void;
}

// @public
export class FormControlDirective extends NgControl implements OnChanges, OnDestroy {
    constructor(validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[], valueAccessors: ControlValueAccessor[], _ngModelWarningConfig: string | null);
    get control(): FormControl;
    form: FormControl;
    set isDisabled(isDisabled: boolean);
    // @deprecated (undocumented)
    model: any;
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    // (undocumented)
    ngOnDestroy(): void;
    get path(): string[];
    // @deprecated (undocumented)
    update: EventEmitter<any>;
    viewModel: any;
    viewToModelUpdate(newValue: any): void;
}

// @public
export class FormControlName extends NgControl implements OnChanges, OnDestroy {
    constructor(parent: ControlContainer, validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[], valueAccessors: ControlValueAccessor[], _ngModelWarningConfig: string | null);
    readonly control: FormControl;
    get formDirective(): any;
    set isDisabled(isDisabled: boolean);
    // @deprecated (undocumented)
    model: any;
    name: string | number | null;
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    // (undocumented)
    ngOnDestroy(): void;
    get path(): string[];
    // @deprecated (undocumented)
    update: EventEmitter<any>;
    viewToModelUpdate(newValue: any): void;
}

// @public
export class FormGroup extends AbstractControl {
    constructor(controls: {
        [key: string]: AbstractControl;
    }, validatorOrOpts?: ValidatorFn | ValidatorFn[] | AbstractControlOptions | null, asyncValidator?: AsyncValidatorFn | AsyncValidatorFn[] | null);
    addControl(name: string, control: AbstractControl, options?: {
        emitEvent?: boolean;
    }): void;
    contains(controlName: string): boolean;
    // (undocumented)
    controls: {
        [key: string]: AbstractControl;
    };
    getRawValue(): any;
    patchValue(value: {
        [key: string]: any;
    }, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    registerControl(name: string, control: AbstractControl): AbstractControl;
    removeControl(name: string, options?: {
        emitEvent?: boolean;
    }): void;
    reset(value?: any, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
    setControl(name: string, control: AbstractControl, options?: {
        emitEvent?: boolean;
    }): void;
    setValue(value: {
        [key: string]: any;
    }, options?: {
        onlySelf?: boolean;
        emitEvent?: boolean;
    }): void;
}

// @public
export class FormGroupDirective extends ControlContainer implements Form, OnChanges, OnDestroy {
    constructor(validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[]);
    addControl(dir: FormControlName): FormControl;
    addFormArray(dir: FormArrayName): void;
    addFormGroup(dir: FormGroupName): void;
    get control(): FormGroup;
    directives: FormControlName[];
    form: FormGroup;
    get formDirective(): Form;
    getControl(dir: FormControlName): FormControl;
    getFormArray(dir: FormArrayName): FormArray;
    getFormGroup(dir: FormGroupName): FormGroup;
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    // (undocumented)
    ngOnDestroy(): void;
    ngSubmit: EventEmitter<any>;
    onReset(): void;
    onSubmit($event: Event): boolean;
    get path(): string[];
    removeControl(dir: FormControlName): void;
    removeFormArray(dir: FormArrayName): void;
    removeFormGroup(dir: FormGroupName): void;
    resetForm(value?: any): void;
    readonly submitted: boolean;
    updateModel(dir: FormControlName, value: any): void;
}

// @public
export class FormGroupName extends AbstractFormGroupDirective implements OnInit, OnDestroy {
    constructor(parent: ControlContainer, validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[]);
    name: string | number | null;
}

// @public
export class FormsModule {
}

// @public
export class MaxLengthValidator implements Validator, OnChanges {
    // (undocumented)
    enabled(): boolean;
    maxlength: string | number | null;
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    registerOnValidatorChange(fn: () => void): void;
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export class MaxValidator extends AbstractValidatorDirective implements OnChanges {
    max: string | number | null;
    ngOnChanges(changes: SimpleChanges): void;
}

// @public
export class MinLengthValidator implements Validator, OnChanges {
    // (undocumented)
    enabled(): boolean;
    minlength: string | number | null;
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    registerOnValidatorChange(fn: () => void): void;
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export class MinValidator extends AbstractValidatorDirective implements OnChanges {
    min: string | number | null;
    ngOnChanges(changes: SimpleChanges): void;
}

// @public
export const NG_ASYNC_VALIDATORS: InjectionToken<(Function | Validator)[]>;

// @public
export const NG_VALIDATORS: InjectionToken<(Function | Validator)[]>;

// @public
export const NG_VALUE_ACCESSOR: InjectionToken<readonly ControlValueAccessor[]>;

// @public
export abstract class NgControl extends AbstractControlDirective {
    name: string | number | null;
    valueAccessor: ControlValueAccessor | null;
    abstract viewToModelUpdate(newValue: any): void;
}

// @public
export class NgControlStatus extends ɵangular_packages_forms_forms_i {
    constructor(cd: NgControl);
}

// @public
export class NgControlStatusGroup extends ɵangular_packages_forms_forms_i {
    constructor(cd: ControlContainer);
}

// @public
export class NgForm extends ControlContainer implements Form, AfterViewInit {
    constructor(validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[]);
    addControl(dir: NgModel): void;
    addFormGroup(dir: NgModelGroup): void;
    get control(): FormGroup;
    get controls(): {
        [key: string]: AbstractControl;
    };
    form: FormGroup;
    get formDirective(): Form;
    getControl(dir: NgModel): FormControl;
    getFormGroup(dir: NgModelGroup): FormGroup;
    // (undocumented)
    ngAfterViewInit(): void;
    ngSubmit: EventEmitter<any>;
    onReset(): void;
    onSubmit($event: Event): boolean;
    options: {
        updateOn?: FormHooks;
    };
    get path(): string[];
    removeControl(dir: NgModel): void;
    removeFormGroup(dir: NgModelGroup): void;
    resetForm(value?: any): void;
    setValue(value: {
        [key: string]: any;
    }): void;
    readonly submitted: boolean;
    updateModel(dir: NgControl, value: any): void;
}

// @public
export class NgModel extends NgControl implements OnChanges, OnDestroy {
    constructor(parent: ControlContainer, validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[], valueAccessors: ControlValueAccessor[]);
    // (undocumented)
    readonly control: FormControl;
    get formDirective(): any;
    isDisabled: boolean;
    model: any;
    name: string;
    // (undocumented)
    static ngAcceptInputType_isDisabled: boolean | string;
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    // (undocumented)
    ngOnDestroy(): void;
    options: {
        name?: string;
        standalone?: boolean;
        updateOn?: FormHooks;
    };
    get path(): string[];
    update: EventEmitter<any>;
    viewModel: any;
    viewToModelUpdate(newValue: any): void;
}

// @public
export class NgModelGroup extends AbstractFormGroupDirective implements OnInit, OnDestroy {
    constructor(parent: ControlContainer, validators: (Validator | ValidatorFn)[], asyncValidators: (AsyncValidator | AsyncValidatorFn)[]);
    name: string;
}

// @public
export class NgSelectOption implements OnDestroy {
    constructor(_element: ElementRef, _renderer: Renderer2, _select: SelectControlValueAccessor);
    id: string;
    // (undocumented)
    ngOnDestroy(): void;
    set ngValue(value: any);
    set value(value: any);
}

// @public
export class NumberValueAccessor extends ɵangular_packages_forms_forms_g implements ControlValueAccessor {
    registerOnChange(fn: (_: number | null) => void): void;
    writeValue(value: number): void;
}

// @public
export class PatternValidator implements Validator, OnChanges {
    // (undocumented)
    ngOnChanges(changes: SimpleChanges): void;
    pattern: string | RegExp;
    registerOnValidatorChange(fn: () => void): void;
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export class RadioControlValueAccessor extends ɵangular_packages_forms_forms_g implements ControlValueAccessor, OnDestroy, OnInit {
    constructor(renderer: Renderer2, elementRef: ElementRef, _registry: ɵangular_packages_forms_forms_r, _injector: Injector);
    fireUncheck(value: any): void;
    formControlName: string;
    name: string;
    // (undocumented)
    ngOnDestroy(): void;
    // (undocumented)
    ngOnInit(): void;
    onChange: () => void;
    registerOnChange(fn: (_: any) => {}): void;
    value: any;
    writeValue(value: any): void;
}

// @public
export class RangeValueAccessor extends ɵangular_packages_forms_forms_g implements ControlValueAccessor {
    registerOnChange(fn: (_: number | null) => void): void;
    writeValue(value: any): void;
}

// @public
export class ReactiveFormsModule {
    static withConfig(opts: {
        warnOnNgModelWithFormControl: 'never' | 'once' | 'always';
    }): ModuleWithProviders<ReactiveFormsModule>;
}

// @public
export class RequiredValidator implements Validator {
    registerOnValidatorChange(fn: () => void): void;
    get required(): boolean | string;
    set required(value: boolean | string);
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export class SelectControlValueAccessor extends ɵangular_packages_forms_forms_g implements ControlValueAccessor {
    set compareWith(fn: (o1: any, o2: any) => boolean);
    registerOnChange(fn: (value: any) => any): void;
    // (undocumented)
    value: any;
    writeValue(value: any): void;
}

// @public
export class SelectMultipleControlValueAccessor extends ɵangular_packages_forms_forms_g implements ControlValueAccessor {
    set compareWith(fn: (o1: any, o2: any) => boolean);
    registerOnChange(fn: (value: any) => any): void;
    value: any;
    writeValue(value: any): void;
}

// @public
export type ValidationErrors = {
    [key: string]: any;
};

// @public
export interface Validator {
    registerOnValidatorChange?(fn: () => void): void;
    validate(control: AbstractControl): ValidationErrors | null;
}

// @public
export interface ValidatorFn {
    // (undocumented)
    (control: AbstractControl): ValidationErrors | null;
}

// @public
export class Validators {
    static compose(validators: null): null;
    // (undocumented)
    static compose(validators: (ValidatorFn | null | undefined)[]): ValidatorFn | null;
    static composeAsync(validators: (AsyncValidatorFn | null)[]): AsyncValidatorFn | null;
    static email(control: AbstractControl): ValidationErrors | null;
    static max(max: number): ValidatorFn;
    static maxLength(maxLength: number): ValidatorFn;
    static min(min: number): ValidatorFn;
    static minLength(minLength: number): ValidatorFn;
    static nullValidator(control: AbstractControl): ValidationErrors | null;
    static pattern(pattern: string | RegExp): ValidatorFn;
    static required(control: AbstractControl): ValidationErrors | null;
    static requiredTrue(control: AbstractControl): ValidationErrors | null;
}

// @public (undocumented)
export const VERSION: Version;

// (No @packageDocumentation comment for this package)

```
